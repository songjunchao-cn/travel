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
        loop: true
      },
      swiperList: [
        {id: '0001', imgUrl: '//dimg04.c-ctrip.com/images/70080t000000ihxn3875C_640_128_25.jpg'},
        {id: '0002', imgUrl: '//dimg04.c-ctrip.com/images/700w0s000000i09wz3A67_640_128_25.jpg'},
        {id: '0003', imgUrl: '//dimg04.c-ctrip.com/images/700i0s000000hwmms3385_640_128_25.jpg'}
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
