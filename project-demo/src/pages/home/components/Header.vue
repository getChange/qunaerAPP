<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont icon-return">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont icon-arrow">&#xe6aa;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/varibles.scss';
.header {
  display: flex;
  height: 0.86rem;
  background: $bgcolor;
  color: #fff;
  line-height: 0.86rem;
  a {
    color: #fff;
  }
  .header-left {
    width: 0.64rem;
    float: left;
    .icon-return {
      font-size: 0.4rem;
      text-align: center;
    }
  }
  .header-right {
    width: 1.24rem;
    float: right;
    text-align: center;
    .icon-arrow {
      font-size: 0.24rem;
    }
  }
  .header-input {
    flex: 1;
    background: #fff;
    border-radius: 0.1rem;
    margin-top: 0.12rem;
    height: 0.64rem;
    line-height: 0.64rem;
    margin-right: 0.2rem;
    color: #ccc;
    padding-left: 0.2rem;
  }
}
</style>
