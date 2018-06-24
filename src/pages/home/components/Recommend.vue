<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item" border-bottom v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src=item.imgUrl>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: '//gw.alicdn.com/bao/uploaded/i2/1990775531/TB2EbVzexk98KJjSZFoXXXS6pXa_!!1990775531.jpg_400x400q75.jpg',
        title: '丽江 | 自由行',
        desc: '云南纯玩旅游全国直飞丽江5天4晚自由行大理香格里拉泸沽湖含机票'},
      {
        id: '0002',
        imgUrl: '//gw.alicdn.com/bao/uploaded/i4/2912596538/TB2ZuFHlStYBeNjSspaXXaOOFXa_!!2912596538.jpg_400x400q75.jpg',
        title: '成都 | 跟团游',
        desc: '四川成都到稻城亚丁旅游7天6晚跟团川西四姑娘山纯玩包车'
      },
      {
        id: '0003',
        imgUrl: '//gw.alicdn.com/bao/uploaded/i2/1911996186/TB2_u7VdmMmBKNjSZTEXXasKpXa_!!1911996186.jpg_400x400q75.jpg',
        title: '大阪 | 自由行',
        desc: '杭州上海直飞日本大阪 5/6天自由行往返特价机票五星酒店京都旅游     '
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top  .2rem
    line-height .8rem
    background  #eee
    text-indent .2rem
  .item
    display flex
    overflow hidden
    height 1.9rem
    .item-img
      width 1.8rem
      height 1.8rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .3rem
        ellipsis()
      .item-desc
        margin-top .1rem
        line-height .44rem
        color #ccc
        font-size .2rem
        ellipsis()
      .item-button
        font-size .25rem
        line-height .44 rem
        margin-top .16rem
        background rgba(0,0,0,.6)
        padding 0 .2rem
        border-radius .06rem
        color #fff
</style>
