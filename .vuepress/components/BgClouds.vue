<template>
  <div class="clouds" style="width:100%;height:100%;">
    <div
      v-for="(stick, index) in sticks"
      :key="stick.sl + Math.random()"
      :class="index % 2==0 ? 'even' : 'odd'"
      :style="{'height' : `calc(100% / ${parseInt(divisions)})`}"
      class="cloud-container"
    >
      <div class="cloud start" :style="{'width' : stick.sl + '%','background-color' : color1}"></div>
      <div
        class="cloud end"
        :style="{'width' : `calc(120% - ${stick.sl}%)`,'background-color' : color2,'border' : `solid thin ${color2}`, 'right' : '0px', transform: 'scale(-1, -1)'}"
      ></div>
    </div>
  </div>
</template>

<script>
import { randomIntFromInterval } from "./util";
export default {
  props: ["color1", "color2", "divisions", "start", "end"],
  data() {
    return { sticks: {} };
  },
  mounted() {
    const sticks = new Array(parseInt(this.divisions)).fill(10).map(val => {
      return {
        sl: randomIntFromInterval(parseInt(this.start), parseInt(this.end))
      };
    });

    this.$data.sticks = sticks;
  }
};
</script>

<style lang="scss" scoped>
:host {
  width: 100%;
  height: 100%;
}

.cloud-container {
  // height: calc(100% / 15);
  position: relative;
}

.cloud {
  height: 100%;
  position: absolute;
  display: inline-block;
  border-top-right-radius: 50px;
  border-bottom-right-radius: 50px;
}

.odd .cloud.end {
  z-index: -10;
}
</style>
