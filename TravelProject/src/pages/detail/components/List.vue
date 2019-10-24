<template>
  <div>
    <div
      class="item"
      v-for="(item,index) of list"
      :key="index"
    >
      <div class="item-title">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
          <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .item-title-icon
    display: inline-block;position: absolute;width: .36rem;height: .36rem;top: .25rem;left: .2rem;background: url(https://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;margin-right: .1rem;background-size: .4rem 3rem;
  .item-title
    position: relative; line-height: .8rem;font-size: .32rem;padding: 0 .6rem;border-bottom:1px solid #e0e0e0;
  .item-children
    padding-left: .4rem;
</style>
