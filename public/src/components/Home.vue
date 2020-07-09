<template>
  <el-row> 
    <el-col :span="16" :offset="4">
      <div class="app-top">
        <app-carousel></app-carousel>
      </div>
      <div class="app-bottom">
        <app-introduction></app-introduction>
      </div>
    </el-col>
  </el-row>
</template>

<script>
import Carousel from './Carousel'
import Introduction from './Introduction'

export default {
  components: {
    appCarousel: Carousel,
    appIntroduction: Introduction,
  }
}
</script>

<style scoped>

.app-top{
  margin-top: 70px;
  height: max-content;
}

.app-bottom {
  margin-top: 70px;
  height: max-content;
}

</style>