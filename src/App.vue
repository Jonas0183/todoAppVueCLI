<template>
  <div id="app">
    <app-head/>
    <list-body/>
  </div>
</template>

<script>
import appHead from './components/appHead.vue'
import ListBody from './components/listBody.vue'

export default {
  components: { appHead, ListBody},
  name: 'App',
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Signika&display=swap');
#app {
  height: 800px;
  background-color: #f0f4ff;
  max-width:800px;
  margin-top: 1vh;
  margin: auto;
  text-align: center;
  font-family: 'Signika', sans-serif;
}
</style>