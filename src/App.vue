<template>
  <div id="app">
    <div class="header">
      Planning Poker
    </div>
    <div class="content">
      <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
      <CardList/>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import CardList from './components/CardList.vue'

export default {
  name: 'app',
  components: {
    CardList
  }
}
</script>

<style>

  html, body {
     height: 100%;
     width: 100%;
     margin: 0;
     padding: 0;
  }

  #app {
    background-color: #f7f7f7;
    color: #616A6B;
    font-family: 'Roboto', sans-serif;
    height: 100%; 
    margin: 0;
    text-align: center;
  }

  .header {
    background-color: #eeeeee;
    font-size: 2.5em;
    height: 125px;
    padding: 30px;
      position: relative;
  }

  .link-button {
    text-decoration: none;
      color: #b4b4b4;
      padding: 10px;
      border: 1px solid #b4b4b4;
      background-color: #fff;
      text-transform: uppercase;
      border-radius: 3px;
      display: inline-block;
  }

  .content {
    align-items: center;
    background-color: #ffffff;
    border-radius: 3px;
    display: flex;
    flex-direction: column;
    margin: 0 auto;
    position: relative;
    top: -5em;
      width: 90%;  
  }

  .hide {
    display: none;
  }
</style>
