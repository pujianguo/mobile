<template>
  <div class="home">
    <common-navbar></common-navbar>

    <div class="container">
    </div>

    <common-footer></common-footer>
  </div>
</template>

<script>
import CommonNavbar from 'components/navbar'
import CommonFooter from 'components/footer'

export default {
  name: 'home',
  props: {
  },
  components: {
    CommonNavbar,
    CommonFooter
  },
  data () {
    return {
    }
  },
  computed: {
  },
  watch: {
  },
  methods: {
  },
  created () {
  },
  mounted () {
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.home
  .header
    width: 100%
    height: 100px
    font-size: 20px
.container{
    width: 100%;
    min-height: 587px;
  }
</style>
