<template>
  <div class="Contentbody">
    <LeftColumn></LeftColumn>
    <RightColumn></RightColumn>
  </div>
</template>

<script>
import LeftColumn from './LeftColumn.vue'
import RightColumn from './RightColumn.vue'
export default {
  components: {
    LeftColumn,
    RightColumn
  }
 
}
</script>

<style>
.Contentbody{
  justify-content: center;
  
  display: flex;
  height: 100vh;
  background-color: #f5f5f5;
  padding: 20px;
  box-sizing: border-box;
  font-family: Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  color: #333;
}
</style>