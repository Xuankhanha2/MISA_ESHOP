<template>
  <div class="wrapper">
    <Navbar_collapse v-if="nav_collapse" @nav_collapse_change="logo_box_click"/>
    <Navbar v-else @nav_collapse_change="logo_box_click"/>
   <div class="main">
      <Header/>
      <Content/>
   </div>
  </div>
</template>

<script>
import Navbar from './components/layout/Navbar.vue'
import Content from './components/layout/Content.vue'
import Navbar_collapse from './components/layout/Navbar_collapse.vue'
import Header from './components/layout/Header.vue'
export default {
  data() {
    return {
      nav_collapse: false
    }
  },
  name: 'App',
  components: {
    Navbar,
    Header,
    Content,
    Navbar_collapse
  }, 
  methods:{
    logo_box_click(){
      this.nav_collapse = !this.nav_collapse; 
    }
  }
}
</script>

<style>
@font-face{
  font-family:  Google-san;
  src: url('~@/assets/font/GoogleSans-Regular.otf');
}
body{
  margin: 0px;
  padding: 0px;
  font-family: Google-san;
}
#app {
 
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.wrapper{

  display: flex;
  flex-wrap: wrap;
}
.main{
  width: calc(100% - 220px);
  height: 100vh;
}
</style>
