<template>
  <div id="app">
    <div class="top_out">
      <div class="top_in">
        <Top/>
      </div>
    </div>
    <div class="works">
      <Works/>
    </div>
    <div class="about">
      <About/>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Top from './components/Top.vue'
import Works from './components/Works.vue'
import Item from './components/Item.vue'
import About from './components/About.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Top,
    Works,
    Item,
    About,
  }
}
</script>

<style>
.top_out{
  height: 100vh;
  width: 100%;
  display: table;
  background-color: #325E35;
}

.top_in{
  display: table-cell;
  vertical-align: middle;
}

.works{
  height: 80vh;

}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  padding: 0px 0px;
  background-color: #F0EFE8;
}
</style>
