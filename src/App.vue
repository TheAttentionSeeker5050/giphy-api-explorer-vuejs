<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>


  <header id="app-header">
  
    <nav id="navbar">
      <div id="header-wrapper">
        
        <img src="https://img.icons8.com/plasticine/100/null/giphy.png" alt="Giphy logo" width="70">
        <h1>GIPHY API EXPLORER</h1>
      </div>

      <ul id="nav-links-wrapper">
        <!-- <li id="search-bar-wrapper"><input type="text" name="searchOption"><button type=""><img src="https://img.icons8.com/ios/50/null/search--v1.png" width="20"/></button></li> -->
        <li ><RouterLink to="/">Home</RouterLink></li>
        <li ><RouterLink to="/about">About</RouterLink></li>

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
