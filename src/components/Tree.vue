<template>
  <div class="tree">
    <ul class="tree-list">
      <node-tree :node="treeData"></node-tree>
    </ul>
  </div>
</template>

<script>
import NodeTree from './NodeTree';

export default {
  name: 'Tree',
  props: {
    treeData: Object
  },
  components: {
    NodeTree
  },
}
</script>

<style scoped>
  .tree-list ul {
    margin: 6px 0;
    padding-left: 16px;
  }
</style>
