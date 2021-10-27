<template>
  <div id="app">
    <tree :tree-data="tree"></tree>
  </div>
</template>

<script>
import * as database from '../public/static/node_modules.json'
import Tree from './components/Tree.vue';

export default {
  name: 'App',
  data: function() {
    return ({
      tree: {...database.default}
    })
  },
  components: {
    Tree
  }
}
</script>

<style>
* {
  list-style-type: none;
  user-select: none;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
