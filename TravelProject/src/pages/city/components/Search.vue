<template>
  <div class="search">
    <input type="text" placeholder="请输入城市名或拼音" class="search-input">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    padding:0 .1rem; height: .72rem;background: $bgColor;
    .search-input
      padding: 0 .1rem;width: 100%;height: .62rem;text-align: center;border-radius: .06rem;color: #666;box-sizing:border-box;
</style>
