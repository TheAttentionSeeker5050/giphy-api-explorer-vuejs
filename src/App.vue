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
    <img src="https://img.icons8.com/plasticine/100/null/giphy.png" alt="Giphy logo">
  
    <nav id="navbar">
      <h1>Giphy api explorer</h1>
      <div id="nav-links-wrapper">
        <ul id="nav-links-list">
          <li><input type="text" name="searchOption"><button type=""><img src="https://img.icons8.com/ios/50/null/search--v1.png"/></button></li>
          <li>Home</li>
          <li>About</li>
        </ul>
      </div>
    </nav>
  
  </header>

  
  

  <RouterView />

  <footer>
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
