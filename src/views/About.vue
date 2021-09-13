<template>
  <div class="tree-menu">
    <div>{{ label }}</div>
    <TreeMenu :label="tree.label" :nodes="tree.nodes"></TreeMenu>
  </div>
</template>
<script>
import TreeMenu from "../components/TreeMenu.vue";
export default {
  components: {
    TreeMenu,
  },
  data() {
    return {
      tree: {
        label: "root",
        nodes: [
          {
            label: "item1",
            nodes: [
              {
                label: "item1.1",
              },
              {
                label: "item1.2",
                nodes: [
                  {
                    label: "item1.2.1",
                  },
                ],
              },
            ],
          },
          {
            label: "item2",
          },
        ],
      },
    };
  },
};
</script>