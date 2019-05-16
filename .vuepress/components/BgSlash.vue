<template>
  <div style="width:100%;height:100%;">
    <div
      class="slash-container"
      :style="{'background' : `linear-gradient(${angle}, ${color1} ${percent1}, ${color2} ${percent2})`}"
    ></div>
  </div>
</template>

<script>
export default {
  props: ["angle", "color1", "percent1", "color2", "percent2"]
};
</script>

<style scoped lang="scss">
.slash-container {
  height: 100%;
  width: 100%;
  //   background: linear-gradient(50deg, #00000000 60%, #2f3441 50%);
}
</style>
