<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for= "item of swiperList" :key="item.id">
        <img :src="item.imgUrl" class="swiper-img">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 4000
      },
      swiperList: [
        {id: '0001', imgUrl: '//gw.alicdn.com/tfs/TB1DHRKzTJYBeNjy1zeXXahzVXa-1125-352.jpg_960x960q90.jpg'},
        {id: '0002', imgUrl: '//gw.alicdn.com/tfs/TB1trLczAyWBuNjy0FpXXassXXa-1125-352.jpg_960x960q90.jpg'},
        {id: '0003', imgUrl: '//gw.alicdn.com/tfs/TB17ZVdyWmWBuNjy1XaXXXCbXXa-1125-352.jpg_960x960q90.jpg'}
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper>>>.swiper-pagination-bullets
    bottom .05rem
  .wrapper>>>.swiper-pagination-bullet-active
    background #fff
  .wrapper>>>.swiper-pagination-bullet
    height .1rem
    width .1rem
  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 31.25%
    .swiper-img
      width 100%
</style>
