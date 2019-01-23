<template>
  <div class="common-navbar">
    <div class="content-box">
      <div class="logo">
        <img src="images/logo-mini.png" alt="logo">
      </div>
      <div class="menu user">
        <div class="menu-icon user-icon" @click="clickUserIcon">
          <span class="iconfont icon-user"></span>
        </div>
      </div>
      <div class="menu project">
        <div class="menu-icon project-icon" @click="clickProjectIcon">
          <span class="iconfont icon-menu"></span>
        </div>
      </div>
    </div>

    <div :class="['user-tip-box', {'show': showUserTip}]">
        <ul class="list">
          <li class="item">
            <span class="text">我的订单</span>
            <span class="iconfont icon-right"></span>
          </li>
          <li class="item">
            <span class="text">我的订单</span>
            <span class="iconfont icon-right"></span>
          </li>
          <li class="item">
            <span class="text">我的订单</span>
            <span class="iconfont icon-right"></span>
          </li>
          <li class="item">
            <span class="text">我的订单</span>
            <span class="iconfont icon-right"></span>
          </li>
        </ul>
        <div class="user-info">
          <span class="name">jianguo5</span>
          <span class="logout">退出</span>
        </div>
      </div>
      <div :class="['project-tip-box', {'show': showProjectTip}]">
        <div :class="['shade', {'show': showProjectTip}]" @click="showProjectTip = false"></div>
        <div class="content">
          <ul class="list">
            <li class="item">
              <span class="text">热门产品</span>
              <span class="iconfont icon-right"></span>
            </li>
            <li class="item">
              <span class="text">云产品</span>
              <span class="iconfont icon-right"></span>
            </li>
            <li class="item">
              <span class="text">我的订单</span>
              <span class="iconfont icon-right"></span>
            </li>
            <li class="item">
              <span class="text">我的订单</span>
              <span class="iconfont icon-right"></span>
            </li>
          </ul>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'common-navbar',
  props: {
  },
  components: {
  },
  data () {
    return {
      showUserTip: false,
      showProjectTip: false
    }
  },
  computed: {
  },
  watch: {
  },
  methods: {
    clickUserIcon () {
      this.showUserTip = !this.showUserTip
    },
    clickProjectIcon () {
      if (this.showUserTip) {
        this.showUserTip = false
      }
      this.showProjectTip = !this.showProjectTip
    }
  },
  created () {
  },
  mounted () {
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.common-navbar{
  position: relative;
  .content-box{
    z-index: 501;
    width: 100%;
    height: $navbar-height;
    background-color: $navbar-bgc;
    position: relative;
    z-index: 500px;
    overflow: hidden;
    .logo{
      position: absolute;
      top: 0;
      left: 0;
      width: 80px;
      height: 50px;
      flex-center();
      img{
        // width: 46px;
        // height: 34px;
      }
    }
    .menu{
      position: absolute;
      top: 0;
      width: 50px;
      height: 50px;
      z-index: 600px;
      &-icon{
        width: 50px;
        height: 50px;
        flex-center();
        color: #fff;
        .iconfont{
          font-size: 20px;
        }
      }
    }
    .user{
      right: 50px;

    }
    .project{
      right: 0;
    }
  }

  .user-tip-box{
    z-index: 499px;
    position: absolute;
    top: -230px;
    left: 0;
    width: 100%;
    height: 230px;
    overflow: hidden;
    background-color: $menu-bgc;
    transition: top .3s;
    &.show{
      top: 50px;
    }
    .list{
      padding: 0 10px 10px;
      color: #fff;
      .item{
        width: 100%;
        height: 40px;
        line-height: 40px;
        font-size: 16px;
        font-weight: bold;
        padding: 0 10px;
        border-bottom: 1px solid #73777A;
        .text{
        }
        .iconfont{
          float: right;
        }
      }
    }
    .user-info{
      overflow: hidden;
      width: 100%;
      height: 60px;
      line-height: 40px;
      font-size: 16px;
      font-weight: bold;
      padding: 0 20px 10px;
      color: #fff;
      flex-between();
      .name{
        max-width: 260px;
        ellipsis();
      }
      .logout{
        padding-left: 30px;
      }
    }
  }

  .project-tip-box{
    z-index: 600;
    position: fixed;
    top:0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: translateX(100%);
    opacity: 0;
    overflow: hidden;
    transition: all .3s;
    display: flex;
    &.show{
      transform: translateX(0);
      opacity: 1;
    }
    .shade{
      width: 60px;
      transition-delay: .3s;
      transition: all .1s;
      // background-color: $shade-bgc;
      &.show{
        background-color: $shade-bgc;
      }
    }
    .content{
      flex: 1;
      overflow-y: auto;
      overflow-x: hidden;
      background-color: #2E2E2E;
      .list{
        color: #fff;
        .item{
          width: 100%;
          height: 40px;
          line-height: 40px;
          font-size: 16px;
          font-weight: bold;
          padding: 0 20px;
          border-bottom: 1px solid #444;
          .text{
          }
          .iconfont{
            float: right;
          }
        }
      }
    }
  }
}
</style>
