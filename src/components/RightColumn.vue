<template>
    <div class="column" id="leftColumn">
        <div v-for="(item, index) in items" :key="index"  class="item">
          <img :src="item.imageUrl" alt="模拟图片">
        </div>
      </div>
  </template>
  
  
  <script>
  import axios from 'axios';
  export default {
      data(){
          return {
              items:[],
              isLoading: false
      }
  },
  mounted() {
      this.fetchItems();
      window.addEventListener('scroll', this.handleScroll);
    },
    beforeDestroy() {
      window.removeEventListener('scroll', this.handleScroll);
    },
  methods: {
      handleScroll() {
      if (window.innerHeight + document.documentElement.scrollTop === document.documentElement.offsetHeight) {
          this.fetchItems();
      }
  },
      // 随机生成长宽，变成参数使用此网站https://placehold.co/， 生产随机尺寸和颜色的图片；
      getRandomImage(width, height) {
          //随机生成颜色
          const bgColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
          const textColor = '#' + Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0');
          return `https://placehold.co/${width}x${height}/${bgColor.substring(1)}/${textColor.substring(1)}`;
      },
      async fetchItems() {
          this.isLoading = true;
          try {
              const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
              this.items = response.data.map(item => ({
                  title: item.title,
                  imageUrl: this.getRandomImage(Math.floor(Math.random() * 200) + 100, Math.floor(Math.random() * 200) + 100)
              }));
          } catch (error) {
              console.error(error);
          } finally {
              this.isLoading = false;
          }
      }
      }
  }
  </script>
  
  <style scoped>
      /* 样式 */
      /* 列 */
     .column {
      display: flex;
      flex-direction: column;
      }
      /* 项 */
      .item {
      margin-bottom: 10px;
      }
      /* 图片 */
     .item img {
      width: 100%;
      }
  </style>