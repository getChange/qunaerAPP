<template>
  <div class="alphabet">
    <ul class="list">
      <li class="item" v-for="(item, key) in cities" :key="key">{{key}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="scss" scoped>
@import '~styles/varibles.scss';
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: .4rem;
  .item {
    text-align: center;
    line-height: .44rem;
    color: $bgcolor;
  }
}
</style>
