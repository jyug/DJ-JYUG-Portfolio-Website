<template>
  
  <el-card class="box-card merchant-category" body-style="padding: 0px;" >
    <el-menu
      default-active="0"
      class="el-menu-vertical-demo"
      background-color="#0d0d0d"
      text-color="#fff"
      active-text-color="#ffd04b">
      <el-menu-item v-for="(category, index) in categories" 
          :key="category"
          :index="index.toString()"
          @click="selectedCategory=category"
          class="merchant-category-item"
      >
          {{ category }}
      </el-menu-item>
    </el-menu>
  </el-card>
      
</template>

<script>
  import { eventBus } from '../main';

  export default {
    data() {
      return {
        categories: ['DJ Controller', 'Standalone DJ System', 
        'Flight Case', 'Headphones', 'Speakers'],
        selectedCategory: 'DJ Controller',
      }
    },
    watch: {
      selectedCategory() {
        eventBus.$emit('selectedCategory', this.selectedCategory);
      }
    }
  }
</script>

<style scoped>
  .merchant-category {
    height: 400px;
    background-color: #0d0d0d;
    color: #fff;
  }

  .merchant-category-item {
    text-align: left;
    display: block;
    height: 100%;
    line-height: 50px;
    padding: 10px 10px 10px 20px;
    margin: 0;
    font-size: 1rem;
  }

  .el-menu {
    /* height: max-content; */
  }

  .merchant-category-item:hover {
    background-color: rgba(240, 255, 255, 0.13)!important;
  }

  .selected {
    color: #ffd04b;
  }
</style>