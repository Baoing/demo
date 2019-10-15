<template>
  <div class="list" ref="wrapper">
    <div class="content">
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">南昌</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"  v-for="item of hotCities" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area"
        v-for="(item,key) of cities"
        :key="item.id"
        :ref="key"
       >
        <div class="title">{{key}}</div>
        <div class="item-list" v-for="subItem of item" :key="subItem.id">
          <div class="item border-topbottom">{{subItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    position: absolute;
    top:1.58rem;left: 0;right: 0;bottom: 0;overflow: hidden;
    .title
      padding-left: .3rem;line-height: .6rem;background: #F5F5F5;font-size: .26rem;
    .button-list
      padding: .1rem .6rem .1rem .1rem;overflow: hidden;
      .button-wrapper
        float: left;width: 33.3%;
        .button
          margin: .1rem;padding: .1rem ;text-align: center;border:.02rem solid #ccc;border-radius:.06rem;
    .item
      padding-left: .2rem;line-height: .64rem;color:#666;
</style>
