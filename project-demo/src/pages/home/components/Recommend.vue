<template>
    <div>
      <div class="recommend-title">热门推荐</div>
      <ul>
        <li class="item" v-for="item of list" :key="item.id">
            <img class="item-img" :src="item.imgUrl" alt="">
            <div class="item-info">
              <p class="item-title">{{item.title}}</p>
              <p class="item-desc">{{item.desc}}</p>
              <button class="item-btn">查看详情</button>
            </div>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="scss" scoped>
  .recommend-title {
    line-height: .8rem;
    background: #eee;
    text-indent: .2rem;
    margin-top: .2rem;
    padding-left: .2rem;
  }
  .item {
    display: flex;
    height: 1.9rem;
    overflow: hidden;
    .item-img {
      width: 1.7rem;
      height: 1.7rem;
      padding: .1rem;
    }
    .item-info {
      padding: .1rem;
      flex: 1;
      min-width: 0;
      .item-title{
        line-height: .54rem;
        font-size: .32rem;
      }
      .item-desc {
        line-height: .4rem;
        font-size: .28rem;
        color: #ccc;
      }
      .item-btn {
        background: #ff9300;
        padding: 0 .2rem;
        border-radius: .06rem;
        margin-top: .16rem;
        color: #fff;
        line-height: .44rem;
      }
    }
  }
</style>
