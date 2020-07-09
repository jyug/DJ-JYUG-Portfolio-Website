<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="12" :offset="0" class="merchant-image">
        <img alt=" " :src="merchant.img">
      </el-col>
      <el-col :span="12" class="merchant-detail">
      <div class="merchant-title"><h3>{{ merchant.title }}</h3></div>
      <div class="merchant-description">{{ merchant.description }}</div>
    </el-col>
    </el-row>
    <el-row>
      <el-col :span="8" :offset="16">
        <el-button round class="purchase-button">Buy on Amazon</el-button>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  export default {
    props: {
      merchant: {
        type: Object,
        required: true,
      }
    },
    data() {
      return {
       
      }
    }
  }
</script>

<style scoped>
  .merchant-image {
   margin-top: 90px;
  }

  .merchant-detail {
    margin-top: 50px;
  }

  img {
    height: 210px;
    width: 300px;
  }

  .merchant-description {
    height: 100px;
    text-align: justify;
    margin-right: 15px;
  }

</style>