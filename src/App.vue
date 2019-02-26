<template>
  <div id="app">
    <div class="header">
      Planning Poker
      <div class="menu-trigger" v-on:click="toggleMenu">
        <i class="fas fa-bars" v-if="!inSettings"></i>
        <i class="fas fa-times" v-if="inSettings"></i>
      </div>
    </div>
    <div class="content">
      <CardList v-if="!inSettings"/>
      <SettingsMenu v-if="inSettings"/>
    </div>
  </div>
</template>

<script>

import CardList from './components/CardList.vue'
import SettingsMenu from './components/SettingsMenu.vue'

export default {
  name: 'app',
  components: {
    CardList,
    SettingsMenu
  },
  data: function () {
      return {
          inSettings: false
      }
  },
  methods: {
    toggleMenu: function () {
        this.inSettings = !this.inSettings
    }
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

  .menu-trigger {
    cursor: pointer;
    display: inline-block;
    font-size: 1em;
    position: absolute;
    right: 50px;
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
