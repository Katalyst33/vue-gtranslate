<template>
  <div>
    <h1>Welcome to my first Plugin</h1>
  </div>
</template>

<script>

export default {

  mounted(){
    this.runTest()
  },

  methods:{
    runTest(){
      console.log("Home Back woods")
    }
  }
}
</script>

<style scoped>

</style>
