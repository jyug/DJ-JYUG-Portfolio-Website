<template>
  <el-card class="box-card">
    <div slot="header" class="clearfix">
      <span class="card-title"><h2>About Me</h2></span>
    </div>
    <el-row class="introduction-content-top">
      <el-col :span="15">
        <div class="text item">
          I'm a professional DJ, developer and content creator located in greater San Diego area.
          I play most EDM genres with an exception of anything hip-hop. My interests are in Liquid Drum & Bass,
          Dubstep and Carnival/Hybrid Trap music. I also love to play Bass House and Future House but 
          don't do these for commercial sets if not explicitly requested.<br><br>
          I record and upload my DJ set videos on Bilibili and will create an YouTube account soon.
          You can find and watch my top videos on this website. For my full video lists and streaming 
          station please visit this <a href="https://space.bilibili.com/309893782">link.</a>
          <br><br>
          I'm a founding member and majority share holder of SoulHunter DJ Club, an raplidly expanding online
          DJ community based on Bilibili. If you would like to join the community please follow this 
          <a href="https://space.bilibili.com/438880875">link.</a>
          
        </div>
      </el-col>
      <el-col :span="8" :offset="1">
        <img src="../assets/carousel/carousel7.jpg" alt=" " class="intro-img">
      </el-col>
    </el-row>
  </el-card>
</template>

<script>

export default {
   
}
</script>

<style scoped>
  .el-card {
    height: inherit;
  }

  .card-title h2 {
    padding-left: 0px;
    text-align: left;
  }

  .text {
    text-align: justify;
    font-size: 1.3rem;
    line-height: 40px;
  }

  .intro-img {
    height: 70%;
    width: 70%
  }

  .introduction-content-top {
    margin-top: 40px;
  }
</style>