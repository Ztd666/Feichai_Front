<template>
  <div id="app">
    <Header></Header>
    <router-view></router-view>
    <Bottom></Bottom>
  </div>
</template>
<script>
  import Header from "@/components/header/Header";
  import Bottom from "@/components/bottom/Bottom";
  export default {
  name: 'App',
    components:{
      Bottom,
      Header
    },
    data(){
      return{
        login:false,
        img:'/unLogin.jpg'
      }
    },
    mounted() {
      setTimeout(() => {
        window.L2Dwidget.init({
          pluginRootPath: 'live2dw/',
          pluginJsPath: 'lib/',
          pluginModelPath: 'live2d-widget-model-z16/assets/',
          tagMode: false,
          debug: false,
          model: { jsonPath: '../live2dw/live2d-widget-model-z16/assets/z16.model.json' },
          display: { position: 'left', width: 150, height: 300 },
          mobile: { show: true },
          log: false
        })
      }, 1000)
    }
  }

</script>

<style>
#app {
  background: transparent !important;
}
</style>
