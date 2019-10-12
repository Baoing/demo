<template>
  <div>
    <div class="recommend-title"><span class="recommend-span">热销推荐</span>
      <ul>
        <li class="item" v-for="item of recommendList" :key="item.id">
          <div class="item-img">
            <img class="item-pic" :src="item.imgUrl">
          </div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1610/16/165075d3fcbe7c8ba3.water.jpg_200x200_dacfbf65.jpg',
        title: '南昌融创海世界',
        desc: '集海洋馆、生物科普、婚庆、表演于一体的海洋馆。'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/ae/ae694b0074546c93a3.img.jpg_200x200_d8d062c6.jpg',
        title: '南昌VR主题乐园',
        desc: '集海洋馆、生物科普、婚庆、表演于一体的海洋馆。'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201407/21/bb285e01da76877f845ffcc463ae5f9a.jpg_200x200_50342a0c.jpg',
        title: '南昌星期8小镇',
        desc: '集海洋馆、生物科普、婚庆、表演于一体的海洋馆。'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1909/3c/3c01881d40474025a3.img.jpg_200x200_94239434.jpg',
        title: '南昌融创乐园',
        desc: '集海洋馆、生物科普、婚庆、表演于一体的海洋馆。'
      }]
    }
  }
}
</script>

<style lang = "stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .recommend-title
    margin-top: .2rem;line-height: .8rem;background-color: #eee;
    .recommend-span
      display: block;text-indent: .2rem;
  .item{display: flex;margin-bottom: .1rem;background: #fff;overflow: hidden;height: 1.9rem;}

      .item-pic
        padding:.1rem; width: 1.7rem;height: 1.7rem;
      .item-info
        flex: 1;padding: .1rem;min-width: 0;
        .item-title
          line-height: .54rem;font-size: .32rem;
        .item-desc
          line-height: .4rem; color: #ccc;ellipsis();
        .item-button
          line-height: .44rem;margin-top: .16rem;background: #ff9300;padding: 0 .2rem;border-radius:.06rem;color:#fff;
</style>
