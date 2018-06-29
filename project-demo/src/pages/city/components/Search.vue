<template>
<div>
  <div class="search">
    <input v-model="keyword" class="search-input" type="text" placeholder="请输入城市名称或拼音">
  </div>
  <div
      class="search-content"
      ref="search"
      v-show="keyword">
    <ul>
      <li
        class="search-item"
        v-for="item of list"
        :key="item.id"
        @click="handleChangeCity(item.name)">{{item.name}}</li>
      <li class="search-item" style="text-align: center" v-show="hasNoData">没有找到匹配数据</li>
    </ul>
  </div>
</div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleChangeCity (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/varibles.scss';
.search {
  height: 0.72rem;
  padding: 0 .1rem;
  background-color: $bgcolor;
  .search-input {
    box-sizing: border-box;
    height: 0.62rem;
    line-height: .62rem;
    padding: 0 .1rem;
    width: 100%;
    text-align: center;
    border-radius: .06rem;
    color: #666;
  }
}
.search-content {
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #eee;
  z-index: 1;
  overflow: hidden;
  .search-item {
    line-height: .62rem;
    padding-left: .2rem;
    border-bottom: 1px solid #e0e0e0
  }
}
</style>
