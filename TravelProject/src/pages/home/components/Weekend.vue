<template>
  <div>
    <div class="recommend-title"><span class="recommend-span">周末去哪儿</span>
      <ul>
        <li class="item" v-for="item of weekendList" :key="item.id">
          <div class="item-img">
            <img class="item-pic" :src="item.imgUrl">
          </div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
  }
}
</script>

<style lang = "stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .recommend-title
    line-height: .8rem;background-color: #eee;
   .recommend-span
      display: block;text-indent: .2rem;
    .item-img{width: 100vw;}
      .item-pic
        padding:.1rem; width: 100%;
    .item-info
      flex: 1;padding: .1rem;min-width: 0;
      .item-title
        line-height: .54rem;font-size: .32rem;color:#000;
      .item-desc
        line-height: .4rem; color: #616161;ellipsis();font-size: .24rem;
</style>
