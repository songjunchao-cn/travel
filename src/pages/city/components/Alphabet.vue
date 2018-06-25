<template>
  <ul class="list">
    <li
    class="item"
    @click="handleLetterClick"
    v-for="item of letters"
    :key="item"
    :ref="item"
    @touchstart="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchend="handleTouchEnd"
    >
      {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Alphabet',
  props: {
    allCities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.allCities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      tiemr: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.tiemr) {
          clearTimeout(this.tiemr)
        }
        this.tiemr = setTimeout(() => {
        const touchY = e.touches[0].clientY - 79
        const index = Math.floor((touchY - this.startY) / 20)
        if (index >= 0 && index <= this.letters.length) {
          this.$emit('change', this.letters[index])
        }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }

  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    position absolute
    top 1.58rem
    right 0
    bottom 0
    width .4rem
    display flex
    flex-direction column
    justify-content center
    .item
      text-align center
      line-height .4rem
      color $bgColor
</style>
