<template>
  <div class="slide-page">
    <div class="wrap">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
}
</script>

<style lang="less" scoped>
.slide-page {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow-y: auto;
  overflow-x: hidden;
  -webkit-overflow-scrolling: touch;
  -webkit-tap-highlight-color:rgba(255,255,255,0);
  -webkit-text-size-adjust: none;
  -webkit-backface-visibility:hidden;-webkit-transform-style:preserve-3d;
  background-position: center;
  transform: translate3d(0,100%,0);
  -webkit-transform: translate3d(0,100%,0);
}
.slide-page.transition {
  transition: all 500ms cubic-bezier(0.550, 0.085, 0.000, 0.990);
  -webkit-transition: all 500ms cubic-bezier(0.550, 0.085, 0.000, 0.990);
}
</style>
