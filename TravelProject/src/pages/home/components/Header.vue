<template>
 <div class="header">
  <div class="header-left">
    <span class="iconfont">&#xe624;</span>
  </div>
  <div class="header-input"><span class="iconfont">&#xe632;</span><input type="text" class="h-input" placeholder="输入城市/景点/游玩主题"></div>
  <router-link to="/City"><div class="header-right">{{this.city}} <span class="iconfont">&#xe64a;</span></div></router-link>
 </div>
</template>

<script>
export default{
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    display: flex;height: $headerHeight;line-height: $headerHeight;background-color: $bgColor;color:#fff;
    .header-left
      float: left;width: .64rem;text-align:center;
    .header-input
      flex:1;height: .64rem;line-height: .64rem;margin-top: .12rem;margin-left: .12rem;padding:0 .2rem;background-color: #fff;
      .h-input
        padding-left: .4rem;width:100%;box-sizing: border-box;
      .iconfont
        position: absolute;color: #999;
    .header-right
      width: 1.24rem;float: right;text-align:center;color:#fff;
      .iconfont
        font-size:.24rem
</style>
