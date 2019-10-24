<template>
  <div>
    <router-link
      tag="div"
      to="/"
      class="header-abs"
      v-show="showAbs"
    >
      <span class="iconfont header-abs-back">&#xe624;</span>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      景点详情
      <router-link to="/"><div class="iconfont header-back">&#xe624;</div></router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        const opacity = top / 140
        this.opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () { // 钩子函数离开本页清空这个函数
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
   @import '~styles/varibles.styl'
  .header-abs
    position: absolute;left: .2rem;top: .2rem;width: .8rem;height: .8rem;line-height: .8rem;text-align:center;border-radius:.4rem;background: #333;
    .header-abs-back
      color:#fff;

  .header-fixed
    position: fixed;left: 0;top: 0;right: 0;height: $headerHeight;line-height: $headerHeight;text-align:center;background: $bgColor;color: #fff;font-size:.32rem;
    .header-back
      position: absolute;top: 0;width: .64rem;color:#fff;
</style>
