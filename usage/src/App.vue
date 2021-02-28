<template>
  <div id="app">

    <h3>I love ice cream</h3>

    <Translator/>
  </div>
</template>

<script>

import Translator from "../../Translator";
// import Translator from "vue-gtranslate";

import "vue-gtranslate/translator.css"

export default {
  name: 'App',
  components: {
    Translator,
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
