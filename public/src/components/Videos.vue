<template>
  <div>
    <div class="video-container">
      <el-row>
        <el-col>
          <h2 class="title">DJ Set Videos</h2>
        </el-col>
      </el-row>
      <el-row class="video-section">
        <el-col :span="22" :offset="1">
          <el-row v-for="(videoRow, index) in videos" :key=index class="video-row">
            <el-col :span="6" v-for="(video, index) in videoRow" :key=index>
                <app-video-card :video="video"></app-video-card>
            </el-col>
          </el-row>
        </el-col>
      </el-row>
      <el-row>
        <el-col>
          <h2 class="title">Product Review Videos</h2>
        </el-col>
      </el-row>
      <el-row class="video-section">
        <el-col :span="22" :offset="1">
          <el-row v-for="(videoRow, index) in reviewVideos" :key=index class="video-row">
            <el-col :span="6" v-for="(video, index) in videoRow" :key=index>
                <app-video-card :video="video"></app-video-card>
            </el-col>
          </el-row>
        </el-col>
      </el-row>
    </div>
    <app-video-player></app-video-player>
  </div>
</template>

<script>
import VideoCard from './VideoCard'
import VideoPlayer from './VideoPlayer'
import { eventBus } from '../main'

import fig1 from '../assets/thumbnails/1.jpg'
import fig2 from '../assets/thumbnails/2.jpg'
import fig3 from '../assets/thumbnails/3.jpg'
import fig4 from '../assets/thumbnails/4.jpg'
import fig5 from '../assets/thumbnails/5.jpg'
import fig6 from '../assets/thumbnails/6.jpg'
import fig7 from '../assets/thumbnails/7.jpg'
import fig8 from '../assets/thumbnails/8.jpg'
import fig9 from '../assets/thumbnails/9.jpg'

export default {
    components:  {
      appVideoCard: VideoCard,
      appVideoPlayer: VideoPlayer,
    },
    data() {
      return {
        thumbnails: [['i2.hdslb.com/bfs/archive/23d38df5b6f6ed5e62e297675c5449f572f59624',
         'i1.hdslb.com/bfs/archive/2a6ee7b348b3e174c1ca84c62f1eb36793e66119', 
         'i2.hdslb.com/bfs/archive/6d5a1f29b8c5b2ba142b87f0760a06620cafebe5', 
         'i1.hdslb.com/bfs/archive/aeddca81ccabbc29277f3a070643815ff4372eed']],
        videos: [[
          {
            thumbnail: fig7,
            videoIframe: 'https://player.bilibili.com/player.html?aid=94435422&bvid=BV1XE411u7hN&cid=161203648&page=1',
            title:  'Bass Drop',
            uploadTime: '2020-03-08',
          },
          {
            thumbnail: fig3,
            videoIframe: 'https://player.bilibili.com/player.html?aid=46057450&bvid=BV11b411e7V6&cid=80691482&page=1',
            title:  'Spacequake',
            uploadTime: '2019-03-11',
          },
          {
            thumbnail: fig5,
            videoIframe: 'https://player.bilibili.com/player.html?aid=47314842&bvid=BV11b411472L&cid=82864780&page=1',
            title:  'Bass & Amp',
            uploadTime: '2019-04-18',
          },
          {
            thumbnail: fig1,
            videoIframe: 'https://player.bilibili.com/player.html?aid=54272408&bvid=BV1P4411n7P3&cid=94935451&page=1',
            title:  'Destination: Atlantis At UCSD',
            uploadTime: '2019-06-02',
          }],
          [
          {
            thumbnail: fig9,
            videoIframe: 'https://player.bilibili.com/player.html?aid=56565415&bvid=BV174411g7PF&cid=98826763&page=1',
            title:  'Bigger',
            uploadTime: '2019-06-23',
          },
          {
            thumbnail: fig8,
            videoIframe: 'https://player.bilibili.com/player.html?aid=51411615&bvid=BV124411v7Ps&cid=89984444&page=1',
            title:  'Pitfall',
            uploadTime: '2019-05-04',
          },
          {
            thumbnail: fig2,
            videoIframe: 'https://player.bilibili.com/player.html?aid=49902404&bvid=BV1gb411V7KJ&cid=87369860&page=1',
            title:  'Soul 02',
            uploadTime: '2019-04-20',
  
          },
          {
            thumbnail: fig6,
            videoIframe: 'https://player.bilibili.com/player.html?aid=60694862&bvid=BV1bt411j7Kx&cid=105636332&page=1',
            title:  'All About That Bass',
            uploadTime: '2019-07-25',
          }
        ]],
        reviewVideos: [[
          {
            thumbnail: fig4,
            videoIframe: 'https://player.bilibili.com/player.html?aid=55648965&bvid=BV164411V7fj&cid=97284617&page=1',
            title:  'Denon DJ Prime 4 Review',
            uploadTime: '2019-06-15',
          }
        ]]
      }
    },
}
</script>

<style scoped>
  .video-container {
    margin-top: 70px;
  }

  .video-row {
    margin-top: 50px;
  }

  .title {
    text-align: left;
    padding-left: 50px;;
  }

  .video-section {
    margin-bottom: 100px;
  }

</style>