<template>
  <div id="app">
    <Top/>
    <div class="works">
      <h2>Works</h2>
      <Works/>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Top from './components/Top.vue'
import Works from './components/Works.vue'
import Item from './components/Item.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Top,
    Works,
    Item
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  padding: 0px 150px;
}
</style>
