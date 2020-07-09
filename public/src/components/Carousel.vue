<template>
  <el-row>
    <el-col :span="20" :offset="2">
      <el-carousel :interval="4000" type="card" :height="imgHeight">
        <el-carousel-item v-for="(item, index) in imgs" :key="index">
          <img :src="item" alt=" ">
        </el-carousel-item>
      </el-carousel>
    </el-col>
  </el-row>
</template>

<script>
import img1 from '../assets/carousel/carousel1.jpg'
import img2 from '../assets/carousel/carousel2.jpg'
import img3 from '../assets/carousel/carousel3.jpg'
import img4 from '../assets/carousel/carousel4.jpg'
import img5 from '../assets/carousel/carousel5.jpg'
import img6 from '../assets/carousel/carousel6.jpg'

export default {
  data() {
    return {
      imgs: [img1, img2, img3, img4, img5, img6],
      windowHeight: window.innerHeight,
      windowWidth: window.innerWidth,
    }
  },
  computed: {
    imgHeight() {
      let height = this.windowWidth / 4.3
      return height.toString() + "px";
    }
  },
  created() {
    window.addEventListener('resize', this.handleResize);
    this.handleResize();
  },
  destroyed() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      this.windowWidth = window.innerWidth;
      this.windowHeight = window.innerHeight;
    }
  }
}
</script>

<style scoped>
  .el-carousel__item img{
   width: 100%;
   height: 100%;
  }
  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
</style>