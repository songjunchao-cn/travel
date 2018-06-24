<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class='icon-img'>
            <img class='icon-img-content' :src='item.imgUrl' />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        autoplay: false
      },
      iconList: [
        {id: '0001', imgUrl: '//gw.alicdn.com/tfs/TB1lw9HfgoQMeJjy0FpXXcTxpXa-225-183.png', desc: '机票'},
        {id: '0002', imgUrl: '//gw.alicdn.com/tfs/TB1KsxcbjihSKJjy0FiXXcuiFXa-225-183.png', desc: '酒店客栈'},
        {id: '0003', imgUrl: '//gw.alicdn.com/tfs/TB1YxNfbjihSKJjy0FlXXadEXXa-225-183.png', desc: '火车票'},
        {id: '0004', imgUrl: '//gw.alicdn.com/tfs/TB1A0hdbaagSKJjy0FhXXcrbFXa-225-183.png', desc: '汽车票'},
        {id: '0005', imgUrl: '//gw.alicdn.com/tfs/TB1G_E.a6ihSKJjy0FeXXbJtpXa-227-183.png', desc: '用车'},
        {id: '0006', imgUrl: '//gw.alicdn.com/tfs/TB1YhCPfgMPMeJjy1XcXXXpppXa-225-183.png', desc: '旅游路线'},
        {id: '0007', imgUrl: '//gw.alicdn.com/tfs/TB1NBJibaagSKJjy0FcXXcZeVXa-225-183.png', desc: '周边游'},
        {id: '0008', imgUrl: '//gw.alicdn.com/tfs/TB1wtlcbjihSKJjy0FfXXbGzFXa-225-183.png', desc: '门票'},
        {id: '0009', imgUrl: '//gw.alicdn.com/tfs/TB13_9IfgoQMeJjy0FpXXcTxpXa-225-183.png', desc: '领里程'},
        {id: '0010', imgUrl: '//gw.alicdn.com/tfs/TB1rv1IfgMPMeJjy1XbXXcwxVXa-227-183.png', desc: '全部'}
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons>>>.swiper-container
    height 0
    padding-bottom 50%
  .icons
    margin-top -.08rem
    .icon
      overflow hidden
      width 25%
      height 0
      padding-bottom 25%
      float left
      position relative
      .icon-img
        position absolute
        top 0
        left 0
        right 0
        buttom .44rem
        box-sizing border-box
        padding .1rem
        .icon-img-content
          display block
          width 100%
          margin 0 auto
      .icon-desc
        position absolute
        left 0
        right 0
        bottom 0
        height .44rem
        line-height .44rem
        text-align center
        color $darkTextColor
        ellipsis()
</style>
