<template>
  <div class="slide-container">
    <slot></slot>
  </div>
</template>

<script>
  import slidePage from 'slidePage'
  export default {
    data () {
      return {
      }
      this.slidePage = null;
    },
    props: {
      refresh: {
        type: Boolean,
        default: true,
      },
      useAnimation: {
        type: Boolean,
        default: true,
      },
      useSwipe: {
        type: Boolean,
        default: true,
      },
      useWheel: {
        type: Boolean,
        default: true,
      },
    },
    mounted() {
      this.$nextTick(function() {
        this.slidePage = new slidePage({
          slideContainer: this.$el,
          slidePages: this.$el.children,
          refresh: this.refresh,
          useWheel: this.useWheel,
          useSwipe: this.useSwipe,
          useAnimation: this.useAnimation,
          before: (origin, direction, target) => {
            this.$emit('before', origin, direction, target)
          },
          after: (origin, direction, target) => {
            this.$emit('after', origin, direction, target)
          },
        })
      })
    },
    methods: {
      update() {
        this.slidePage.update(this.$el.children);
      },
      destroy() {
        this.slidePage.destroy();
      },
      slideFire(page) {
        this.slidePage.slideFire(page)
      },
      slideTo(page) {
        this.slidePage.slideTo(page)
      },
      slideNext() {
        this.slidePage.slideNext()
      },
      slidePrev() {
        this.slidePage.slidePrev()
      }
    }
  }
</script>

<style lang="less" scoped>
  /* 自定义容器样式 */
  .slide-container {
    width: 100%;
    height: 100%;
    overflow: hidden;
    position: relative;
  }
</style>
