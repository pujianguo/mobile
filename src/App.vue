<template>
  <div id="app">
    <router-view/>
  </div>
</template>
<script>
export default {
  methods: {
    rem () {
      let t = 100
      let o = 750
      let e = document.documentElement.clientWidth || window.innerWidth
      let n = Math.max(Math.min(e, 480), 320)
      let h = 50
      if (n <= 320) {
        h = Math.floor(n / o * t * 0.99)
      } else if (n > 320 && n <= 362) {
        h = Math.floor(n / o * t * 1)
      } else if (n > 362 && n <= 375) {
        h = Math.floor(n / o * t * 1)
      } else { // n > 375
        h = Math.floor(n / o * t * 0.97)
      }
      document.querySelector('html').style.fontSize = h + 'px'
    }
  },
  created () {
    document.addEventListener('DOMContentLoaded', () => {
      this.rem()
    })
    window.addEventListener('resize', () => {
      this.rem()
    })
  }
}
</script>
<style lang="stylus" scoped>

</style>
