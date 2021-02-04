<template>
  <div id="app">
    <upperComponent/>
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import upperComponent from "./components/upperComponent.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    upperComponent,
  },
};
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.space-between{
    justify-content: space-between;
}
.justify-center{
  justify-content: center;
}
.align-center{
  align-items: center;
}
.d-block{
  display: block;
}
.d-flex{
  display: flex;
}
.flex-column{
  flex-direction: column;
}
.d-inline{
  display: inline;
}
</style>
