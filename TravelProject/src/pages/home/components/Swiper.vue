<template>
  <div class="wrapper">
    <swiper :options = "swiperOption">
      <swiper-slide
        v-for = "item of swiperList"
        :key = "item.id"
      >
        <img class="swiper-img" :src="item.imgUrl" alt>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1610/f3/f39d9de1e92deb02.jpg_750x200_8cbc3f9b.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1609/eb/29c87b49de782d02.jpg_750x200_fd83c4f3.jpg'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1609/1b/371522f509580f02.jpg_750x200_8d978cde.jpg'
      }, {
        id: '0004',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201910/78b240572657a6da67e662540c846dd6.jpg_750x200_b75c8be9.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .wrapper >>> .swiper-pagination-bullet-active
      background: #fff !important;
  .wrapper
     width: 100%;height: 0;padding-bottom: 26.66%;overflow: hidden;background:#eee;
    .swiper-img
      width: 100%;

</style>
