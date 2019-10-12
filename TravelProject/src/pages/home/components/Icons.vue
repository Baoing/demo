<template>
  <div class="icons">
    <swiper :options = "swiperOption">
      <swiper-slide
        v-for = "page of pages"
        :key ="page.index"
      >
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img :src="item.iconUrl" alt>
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        loop: false
      },
      iconList: [{
        id: '0001',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '0002',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
        desc: '夏日玩水'
      }, {
        id: '0003',
        iconUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
        desc: '自然风光'
      }, {
        id: '0004',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
        desc: '亲子游玩'
      }, {
        id: '0005',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
        desc: '游乐场'
      }, {
        id: '0006',
        iconUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/2d83d4e0f56b2e54c007079f905293e3.png',
        desc: '滕王阁'
      }, {
        id: '0007',
        iconUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/730646c021800ebd1385872fe6212476.png',
        desc: '狮子峰'
      }, {
        id: '0008',
        iconUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/e40f084b7be74a288e77be40b2b38720.png',
        desc: '金燕国际温泉'
      }, {
        id: '0009',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '融创乐园'
      }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .icons >>> .swiper-container
    height: 0;padding-bottom: 50%;
  .icons
    margin-top: .1rem;padding-bottom: 50%;height: 0;overflow: hidden;
    .icon
      position: relative; padding-bottom: 25%;height: 0;width: 25%;float: left;
      .icon-img
        position absolute;top: 0;left: 0;right: 0;bottom: .44rem;text-align:center;box-sizing: border-box;padding: .1rem;
        img
          height: 100%;
      .icon-desc
        position:absolute;left: 0;right: 0;bottom: 0;height: .44rem;line-height: .44rem;color:$darkTextColor;text-align:center;

</style>
