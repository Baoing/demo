<template>
  <div>
    <div class="search">
      <input type="text" v-model='keyword' placeholder="请输入城市名或拼音" class="search-input">
    </div>
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li class="search-item  border-bottom" v-for="item of list" :key="item.id" @click="handleCity(item.name)">{{item.name}}</li>
        <li class="search-item  border-bottom" v-show="hasNodata">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  props: {
    cities: Object
  },
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCity (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search, {click: true})
  },
  computed: {
    hasNodata () {
      return !this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    padding:0 .1rem; height: .72rem;background: $bgColor;
    .search-input
      padding: 0 .1rem;width: 100%;height: .62rem;text-align: center;border-radius: .06rem;color: #666;box-sizing:border-box;
  .search-content
    position: absolute;top: 1.58rem;left: 0;right: 0;bottom: 0;background: #fff;overflow: hidden;z-index:10;
    .search-item
     padding-left: .2rem;line-height: .64rem;color:#666;

</style>
