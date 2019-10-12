<template>
  <div class="header">
    城市选择
    <router-link to="/"><div class="iconfont header-back">&#xe624;</div></router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
    .header
      height: $headerHeight;line-height: $headerHeight;text-align:center;background: $bgColor;color: #fff;font-size:.32rem;overflow: hidden;
      .header-back
        position: absolute;top: 0;width: .64rem;color:#fff;
</style>
