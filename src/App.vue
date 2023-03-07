<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->

  <header id="app-header">
  
    <nav id="navbar">
      <div id="header-wrapper">
        
        <img src="https://img.icons8.com/plasticine/100/null/giphy.png" alt="Giphy logo" width="70px">
        <h1>Giphy api explorer</h1>
      </div>

      <ul id="nav-links-wrapper">
        <li id="search-bar-wrapper"><input type="text" name="searchOption"><button type=""><img src="https://img.icons8.com/ios/50/null/search--v1.png" width="20"/></button></li>
        <li class="hide-on-mobile">Home</li>
        <li class="hide-on-mobile">About</li>
        <li class="display-on-mobile"><img src="https://img.icons8.com/external-tal-revivo-bold-tal-revivo/24/null/external-horizontal-separated-bars-representing-hamburger-menu-layout-grid-bold-tal-revivo.png" width="20"/></li>

      </ul>
    </nav>
  
  </header>

  
  

  <RouterView />

  <footer id="footer">
    <p>Made by 
      <a href="https://nicolas-castellano.com/" target="_blank">Nicolas Castellano</a>
    </p>
    <p>Powered by 
      <a href="https://developers.giphy.com/" target="_blank">Giphy</a>
    </p>
  </footer>

</template>

<style scoped>



</style>
