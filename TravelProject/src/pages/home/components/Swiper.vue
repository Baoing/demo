<template>
  <div class="wrapper">
    <swiper :options = "swiperOption" v-if="showSwiper">
      <swiper-slide
        v-for = "item of list"
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
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .wrapper >>> .swiper-pagination-bullet-active
      background: #fff !important;
  .wrapper
     width: 100%;height: 0;padding-bottom: 31.66%;overflow: hidden;background:#eee;
    .swiper-img
      width: 100%;

</style>
