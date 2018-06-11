<template>
  <div class="header">
    <div class="header-left">left</div>
    <div class="header-input">input</div>
    <div class="header-right">right</div>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="scss" scoped>
.header {
  height: .86rem;
 .header-left {
   width: .64rem;
   float: left;
 }
 .header-right {
   width: 1.24rem;
   float: right;
 }
}
</style>
