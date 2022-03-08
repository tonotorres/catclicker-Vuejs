<template>
  <div class="main-menu">
    <div class="nav-bar">
      <img class="logo" src="./assets/images/logo.png">
      <p class="title">CAT-CLIKER</p>
    </div>
    
    <cat-manager/>
  </div>
</template>

<script>
import CatManager from './components/CatManager.vue'

export default {
  name: 'App',
  components: {
    CatManager
  }
}
</script>

<style>
html {
  background-color: #8BC6EC;
  background-image: linear-gradient(135deg, #1c6a9e 0%, #101575 100%);
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  font-family: 'Courier New', Courier, monospace;
  font-size: 18px;
  font-weight: 100;
  color: rgba(255, 255, 255, 1);
  text-transform: none;
  font-style: normal;
  text-decoration: none;
  line-height: 1.4em;
  letter-spacing: 0px;
  height: 100%;
  overflow: auto;
}
body { 
    background-color: transparent !important;
    height: 100%;
    overflow: auto;
}
.nav-bar {
  display: flex;
  vertical-align: middle;
}
.logo {
  height: 5%;
  width: 5%;
  margin-left: 1%;
}
.title {
  font-size: 200%;
  margin-top: auto;
  margin-bottom: auto;
  padding-top: 1%;
  color: white;
  font-family: 'Courier New', Courier, monospace;
}
</style>
