<template>
  <div>
      <NavigationList1></NavigationList1>
      <input type="text" v-model="searchText" placeholder="🔍大家都在搜“妆容画廊">
      <NavigationList2></NavigationList2>
  </div>
</template>

<script>
import NavigationList1 from './NavigationList1.vue';
import NavigationList2 from './NavigationList2.vue';
export default {
  components: {
    NavigationList1,
    NavigationList2
  },
  data() {
      return {
          searchText: ''
      };
  }
};
</script>

<style scoped>
/* 可以添加组件特定样式 */
input{
  width: 500px;
  padding: 5px;
  /* 默认内容在中间 */
  text-align: center;
}
</style>