<template>
  <div id="app">
    <upper-component />
    <lower-component />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import LowerComponent from "./components/lowerComponent/lowerComponent.vue";
import upperComponent from "./components/upperComponent/upperComponent.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    upperComponent,
    LowerComponent,
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
body {
  font-family: "Larsseit";
  color: #fff;
  background-color: #011627;
}
@font-face {
  font-family: "Larsseit";
  src: url("./assets/fonts/Larsseit.eot");
  src: url("./assets/fonts/Larsseit.eot?#iefix") format("embedded-opentype"),
    url("./assets/fonts/Larsseit.woff2") format("woff2"),
    url("./assets/fonts/Larsseit.woff") format("woff"),
    url("./assets/fonts/Larsseit.ttf") format("truetype");
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}
@font-face {
  font-family: "Noe Display";
  src: url("./assets/fonts/NoeDisplay-Bold.eot");
  src: url("./assets/fonts/NoeDisplay-Bold.eot?#iefix")
      format("embedded-opentype"),
    url("./assets/fonts/NoeDisplay-Bold.woff2") format("woff2"),
    url("./assets/fonts/NoeDisplay-Bold.woff") format("woff"),
    url("./assets/fonts/NoeDisplay-Bold.ttf") format("truetype");
  font-weight: bold;
  font-style: normal;
  font-display: swap;
}

.flex-wrap{
  flex-wrap: wrap;
}
.space-between {
  justify-content: space-between;
}
.justify-center {
  justify-content: center;
}
.align-center {
  align-items: center;
}
.d-block {
  display: block;
}
.d-flex {
  display: flex;
}
.flex-column {
  flex-direction: column;
}
.d-inline {
  display: inline;
}
</style>
