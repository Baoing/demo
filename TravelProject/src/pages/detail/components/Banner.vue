<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="info-tit">{{ sightName }}</div>
        <div class="info-pic"><span class="iconfont">&#xe692;</span> {{ this.bannerImgs.length }}</div>
      </div>
    </div>
    <common-fade>
      <common-gallary
        :imgs="bannerImgs"
        v-if="showGallary"
        @close="handleGallaryClick"
      ></common-gallary>
    </common-fade>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import CommonFade from 'common/fade/Fade'

export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array

  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClick () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary,
    CommonFade
  }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .banner
      position: relative; width: 100%; height: 0;padding-bottom: 55%;
      img
        width: 100%;
      .banner-info
        position: absolute;bottom: 0;display: flex;width: 100vw;line-height: .6rem;font-size: .32rem;color:#fff;background: linear-gradient(rgba(0, 0, 0, 0),rgba(0, 0, 0, .7))
        .info-tit
          padding-left: .2rem;width: 84vw;text-shadow: 0 1px 2px rgba(0,0,0,0.70);
        .info-pic
          padding-right: .2rem;flex: 1;
</style>
