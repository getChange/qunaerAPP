<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="请输入城市名称或拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="scss" scoped>
@import '~styles/varibles.scss';
.search {
  height: 0.72rem;
  padding: .1rem;
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
</style>
