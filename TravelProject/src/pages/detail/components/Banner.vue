<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img src="http://img1.qunarzz.com/sight/p0/1610/fd/fde9fe8351066dc4a3.water.jpg_600x330_fa6c9df4.jpg" alt="">
      <div class="banner-info">
        <div class="info-tit">南昌融创海世界</div>
        <div class="info-pic"><span class="iconfont">&#xe692;</span> 29</div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-if="showGallary"
      @close="handleGallaryClick"
    ></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1610/fd/fde9fe8351066dc4a3.water.jpg_r_800x800_adee854d.jpg', 'http://img1.qunarzz.com/sight/p0/1910/ea/ea8e28450f5c6fa6a3.img.png_r_800x800_ec37702f.png', 'http://img1.qunarzz.com/sight/p0/1712/17/175c586fa6d987d9a3.img.png_r_800x800_dab46904.png']
    }
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
    CommonGallary
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
