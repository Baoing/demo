<template>
 <div class="header">
  <div class="header-left">
    <span class="iconfont">&#xe624;</span>
  </div>
  <div class="header-input"><span class="iconfont">&#xe632;</span><input type="text" class="h-input" placeholder="输入城市/景点/游玩主题"></div>
  <div class="header-right">城市 <span class="iconfont">&#xe64a;</span></div>
 </div>
</template>

<script>
export default{
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    display: flex;height: .86rem;line-height: .86rem;background-color: $bgColor;color:#fff;
    .header-left
      float: left;width: .64rem;text-align:center;
    .header-input
      flex:1;height: .64rem;line-height: .64rem;margin-top: .12rem;margin-left: .12rem;padding:0 .2rem;background-color: #fff;
      .h-input
        padding-left: .4rem;width:100%;box-sizing: border-box;
      .iconfont
        position: absolute;color: #999;
    .header-right
      width: 1.24rem;float: right;text-align:center;
      .iconfont
        font-size:.24rem
</style>
