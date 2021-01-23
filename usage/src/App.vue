<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Usage</h1>
    <p>I love ice cream</p>
    <p>i am hungry now</p>
    <Translator/>

  </div>
</template>

<script>

import Translator from "../../Translator";

export default {
  name: 'App',
  components: {
Translator
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
