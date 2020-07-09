<template>
  <el-dialog
  title=""
  :visible.sync="Visible"
  width="0%"
  top="10vh"
  :show-close="false"
  center>
    <iframe 
      :src="iframe" 
      scrolling="no" border="0" 
      frameborder="no" framespacing="0" 
      allowfullscreen="true"> 
    </iframe>
  </el-dialog>
</template>

<script>
import { eventBus } from '../main'

export default {
    props: {
      // visible: {
      //   type: Boolean,
      //   required: true,
      // }
    },
    data() {
      return {
        Visible: false,
        iframe: ''
      };
    },
    watch: {
      Visible() {
        if (!this.Visible) {
          this.iframe = '';
        }
      }
    },
    created() {
      eventBus.$on("playerTriggered", (data) =>{
        this.Visible = true;
        this.iframe = data;
      });
    }
}
</script>

<style scoped>
  iframe {
    height: 60%;
    width: 50%;
    position: fixed;
    left: 22.3%;
    top: 20%;
  }


</style>