<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" @click="handleCityClick(item.name)" v-for="item of hotCities" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of allCities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div @click="handleCityClick(innerItem.name)" class="item border-bottom" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'List',
  props: {
    hotCities: Array,
    allCities: Object,
    letter: String
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    ...mapMutations(['changeCity']),
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    }
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color #ccc
    &:after
      border-color #ccc
  .list
    position absolute
    top 1.6rem
    left 0
    right 0
    bottom 0
    overflow hidden
    .border-bottom
      &:before
        border-color #ccc
    .title
      height .6rem
      line-height .6rem
      background #eee
      padding-left .2rem
      color #666
      font-size .26rem
     .button-list
       padding .1rem .6rem .1rem .1rem
       overflow hidden
       .button-wrapper
         cursor: pointer
         float left
         width 33.3%
         .button
           margin .1rem
           padding .1rem 0
           text-align center
           border .02rem solid #ccc
           border-radius .06rem
    .item-list
      background #fff
      .item
        line-height .76rem
        padding-left .2rem
        cursor: pointer;
</style>
