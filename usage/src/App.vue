<template>
  <div id="app">

    <router-view/>
    <Translator />

  </div>
</template>

<script>
import Translator from "../../Translator";
import "vue-gtranslate/translator.css"

export default {
  components: {
    Translator
  },

  computed: {
    currentRouteName() {
      if (this.$route.path === "/") {
        return `${this.$route.path}`;
      } else {
        return `${this.$route.path}/`;
      }
    }
  },

  methods: {




  }


}
</script>

<style scoped>

</style>
