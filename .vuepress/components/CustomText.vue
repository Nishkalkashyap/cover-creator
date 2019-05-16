<template>
  <div>
    <div class="texttt" :style="realStyles">{{content}}</div>
  </div>
</template>

<script>
export default {
  props: ["content", "styles"],
  data() {
    return {
      realStyles: {}
    };
  },
  mounted() {
    // console.log(this.styles, 'styles');
    this.$data.realStyles = JSON.parse(this.styles || {});
  }
};
</script>

<style lang="scss" scoped>
div.texttt {
  position: absolute;
  top: 100px;
  left: 100px;
  color: red;
  font-size: 30px;
  font-weight: 700;
}
</style>
