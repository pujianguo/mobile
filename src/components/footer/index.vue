<template>
  <div class="common-footer">
    <div class="project-footer">
      <span class="copyright">2017-2018 © Powered by </span>
      <span href="mailto:sce@staff.sina.com.cn" class="developer">弹性云计算平台</span>
      </div>
  </div>
</template>

<script>
export default {
  name: 'common-footer',
  props: {
  },
  components: {
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

.common-footer
  width: 100%
  height: 30px
  background-color: $footer-bgc
  color: $footer-color
  font-size: 12px
  flex-center()
</style>
