<template>
  <div class="side-container" :class="{ active: isOpened }">
    <a v-for="trip in myTrips" :key="trip.id" href="#">{{ trip.tripName }}</a>
  </div>
</template>

<script>
import json from "../../trips.json";
export default {
  props: {
    isOpened: Boolean,
  },
  data() {
    return {
      myTrips: json,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.side-container {
  position: absolute;
  max-width: 350px;
  width: 100%;
  left: -350px;
  top: 0;
  height: 100%;
  background-color: #011627;
  padding-top: 32px;
  transition: left 0.5s;
  z-index: 2;
}
.side-container.active {
  left: 0;
}
.side-container a {
  display: block;
  width: 75%;
  margin: 16px auto;
  padding: 0 16px;
  line-height: 3;
  background-color: #00c9e0;
  border-radius: 16px;
  text-decoration: none;
  color: #fff;
  position: relative;
  left: -100%;
  transition: all 0.6s;
}
.side-container.active a {
  left: 0;
}
.side-container a:hover {
  background-color: #009eaf;
}
@media only screen and (max-width: 767.5px) {
  .side-container {
    max-width: 75%;
  }
}
</style>
