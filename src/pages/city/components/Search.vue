<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="请输入城市名或者拼音">
    </div>
    <div class="search-content" v-show="keyword.length" ref="search">
      <ul>
        <li class="search-item border-bottom" v-for="item in list" :key="item.id">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="noMatch">无匹配城市</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'Search',
  props: {
    allCities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    noMatch () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.allCities) {
          this.allCities[i].forEach((value) => {
            if (value.name.indexOf(this.keyword) > -1 || value.spell.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
        if (!this.keyword) {
          this.list = []
        }
      }, 50)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height .72rem
    padding 0 .1rem
    background $bgColor
    .search-input
      box-sizing border-box
      width 100%
      height .62rem
      line-height .62rem
      text-align center
      border-radius .06rem
      color #666
      padding 0 .1rem
  .search-content
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    background #ccc
    z-index 1
    .search-item
      line-height .62rem
      padding-left .2rem
      color #666
      background #fff
</style>
