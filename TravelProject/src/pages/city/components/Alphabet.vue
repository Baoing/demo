<template>
  <ul class="list">
    <li class="item"
      v-for="(item,key) of cities"
      :key="item.id"
      @click="handleLetterClick"
    >
      {{key}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Alphabet',
  props: {
    cities: Object
  },
  methods: {
    handleLetterClick: function (e) {
      this.$emit('change', e.target.innerText)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display: flex;flex-direction: column;justify-content: center; position: absolute;right: 0;top: 1.58rem;bottom: 0;width: .4rem;
    .item
      line-height: .4rem;text-align: center;color:$bgColor;
</style>
