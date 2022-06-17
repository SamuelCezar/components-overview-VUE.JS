<template>
  <h1>Local Component</h1>
  <h2>{{ title }}</h2>
  <!--<button @click="$emit('addClick')">Add</button>-->
  <button @click="$emit('addClick', 1)">Add</button>
  <button @click="addTwo">Add Two</button>
    <br/>
  <!--<slot></slot>-->
  <slot name="header"/>
  <br/>
  <slot name="content"/>
</template>

<script>
export default {
  //props: ["title"],
  props: {
    title: String,
  },
  methods: {
    addTwo() {
      this.$emit("addClick", 2);
    },
  },
};
</script>

<style scoped>
</style>
