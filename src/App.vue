<template>
  <div id="app">
    <next-tick class="components"></next-tick>
    <directives class="components"></directives>
  </div>
</template>

<script>
import NextTick from './components/nextTick.vue'
import Directives from './components/directives.vue'
export default {
  name: 'app',
  components: {
    NextTick,
    Directives
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
  .components{
    margin: 50px 100px;
    border: solid 1px #ddd;
  }
h1 {
  font-weight: normal;
}
  .title{
    float: left;
    font-size: 18px;
    border-bottom: solid 1px #41B883;
    padding: 20px 20px;
  }
.content{
  margin: 20px 20px;
}
  .clear{
    clear: both;
  }
  .remark{
    margin: 20px 20px;
    padding: 20px 20px;
    background-color: #7DCEAA;
    color: #fff;
    line-height: 40px;
  }
</style>
