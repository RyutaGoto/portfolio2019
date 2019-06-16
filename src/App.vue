<template>
  <div id="app">
    <div class="top_out">
      <div class="top_in">
        <Top/>
      </div>
    </div>
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
.top_out{
  height: 100vh;
  width: 100%;
  display: table;
}

.top_in{
  display: table-cell;
  vertical-align: middle;
}

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
