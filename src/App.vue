<template>
  <global-component></global-component>
  <local-component :title="title" @addClick="count += $event">
    <!--Slot Test-->
    <template v-slot:header> Slot Header </template>
    <template v-slot:content> Slot Content </template>
  </local-component>
  <p>{{ count }}</p>
</template>

<script>
import LocalComponent from "./components/LocalComponent.vue";

export default {
  data() {
    return {
      title: "Component Title",
      count: 0,
    };
  },
  computed: {
    computedTitle() {
      return "Teste" + this.title;
    },
  },
  methods: {},
  components: {
    LocalComponent,
  },

  //Hooks de inicialização
  beforeCreate() {
    console.log("beforeCreate", this.title);
  },
  created() {
    console.log("created", this.title, this.computedTitle);
  },
  //Hooks de montagem
  beforeMount() {
    console.log("Before mount");
  },
  mounted() {
    console.log("mounted");
  },
  //Hooks de atualização
  beforeUpdate() {
    console.log("Before update");
  },
  updated(){
    console.log("updated")
  },
  //Hooks de destruição
  beforeUnmount() {
    console.log("Beforeunmount")
  },
  unmounted(){
    console.log("unmounted")
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
