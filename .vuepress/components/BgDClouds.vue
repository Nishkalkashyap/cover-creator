<template>
  <div class="parent-container">
    <div class="item">
      <BgClouds :color1="color1" :color2="color2" :divisions="divisions" :start="start" :end="end"/>
    </div>
    <div class="item reverse">
      <BgClouds :color1="color1" :color2="color2" :divisions="divisions" :start="start" :end="end"/>
    </div>
  </div>
</template>

<script>
export default {
  props: ["color1", "color2", "divisions", "start", "end"]
};
</script>

<style lang="scss" scoped>
.parent-container {
  height: 100%;
  display: flex;

  .item {
    width: 50%;
    height: 100%;
    display: inline-block;
    position: relative;
  }

  .reverse {
    transform: scale(-1, -1);
    left: -1px;
  }
}
</style>
