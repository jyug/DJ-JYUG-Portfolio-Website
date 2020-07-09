<template>
  <div>
    <el-card 
      class="box-card" 
      shadow="always" 
      :body-style="cardBodyStyle"
    >
      <img alt="" :src="video.thumbnail"
      @click="playVideo">
      <div style="padding: 14px;">
        <span>{{video.title}}</span>
        <div>
          <time class="time">{{ video.uploadTime}}</time>
        </div>
      </div>
    </el-card>
  </div>
</template>

<script>
  import VideoPlayer from './VideoPlayer'
  import { eventBus } from '../main'

  export default {
      props: {
        video: {
          type: Object,
          required: true,
        }
      },
      data() {
        return {
          cardBodyStyle: {
            padding: '0px',
          }
        }
      },
      methods: {
        playVideo() {
          eventBus.$emit("playerTriggered", this.video.videoIframe);
          console.log("clicked");
        }
      }
  }
</script>

<style scoped>
  .el-card img {
    width: 100%;
    height: 80%;
  }

  .el-card {
    width: 80%;
    height: 80%;
    border: 0px;
    padding: 0px;
  }

  .el-card img:hover {
    width: 100%;
    height: 100%;
  }

  .el-card:hover {
    width: 90%;
    height: 90%;
  }

  iframe {
    height: 400px;
    width: 600px;
  }

  .time {
    font-size: 13px;
    color: #999;
  }
</style>