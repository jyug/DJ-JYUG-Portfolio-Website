<template>
  <div id="app">
    <el-row> 
      <app-nav></app-nav>
    </el-row>
    <component :is="activeComponent"></component>
    <el-row>
      <el-col :span="24" :offset="0">
        <app-footer></app-footer>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import Nav from './components/Nav'
import Home from './components/Home'
import Videos from './components/Videos'
import Merchants from './components/Merchants'
import Footer from './components/Footer'
import { eventBus } from './main'

export default {
  components: {
    appNav: Nav,
    appHome: Home,
    appVideos: Videos,
    appFooter: Footer,
    appMerchants: Merchants,
  },
  data () {
    return {
      activeComponent: 'appHome',
    } 
  },
  created() {
    eventBus.$on('menuItemSelected', (data) => {
      this.activeComponent = data;
    });
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #ffd04b;
  }
</style>
