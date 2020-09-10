<template>
  <el-card class="box-card" shadow="never">
    <el-row>
      <el-col :span=12 :offset=6>
        <div class="amazon-disclamier">
          DJJYUG.com is a participant in the Amazon Services LLC Associates Program, 
          an affiliate advertising program designed to provide a means for sites to earn advertising fees 
          by advertising and linking to Amazon.com. As an Amazon Associate I earn from qualifying purchases.
        </div>
      </el-col>
    </el-row>
    <div class="text">
      ©2020 JYUG
    </div>
  </el-card>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
  .el-card {
    margin-top: 100px;
    height: 200px;
    background-color: #0d0d0d;
    border: none;
  }

  .text {
    position: absolute;
    top: 80%;
    left: 90%;
    color: #fff;
    text-align: center;

  }

  .amazon-disclamier {
    color: #fff;
    text-align: center;
    font-size: 14px;
    margin-top: 50px
  }
</style>