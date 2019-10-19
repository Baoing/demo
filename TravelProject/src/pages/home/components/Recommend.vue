<template>
  <div>
    <div class="recommend-title"><span class="recommend-span">热销推荐</span>
      <ul>
        <router-link tag="li"
          class="item"
          v-for="item of recommends"
          :key="item.id"
          :to="'/detail/'+item.id"
        >
          <div class="item-img">
            <img class="item-pic" :src="item.imgUrl">
          </div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
        </router-link>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommends: Array
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
