<template>
  <transition name="slide">
    <div class="side-container" v-if="isOpened">
      <sequential-entrance fromRight>
        <a v-for="trip in myTrips" :key="trip.id" href="#">{{
          trip.tripName
        }}</a>
      </sequential-entrance>
    </div>
  </transition>
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
  position: fixed;
  max-width: 350px;
  width: 100%;
  top: 0;
  right: 0;
  height: 100%;
  background-color: #011627;
  padding-top: 32px;
  transition: right 0.5s;
  z-index: 2;
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
}
.side-container a:hover {
  background-color: #009eaf;
}
.slide-enter-active,
.slide-leave-active {
  transition: right 0.5s ease-in-out;
}
.slide-enter-active {
  right: -350px;
}
.slide-leave-active {
  right: 0;
}

.slide-enter-from,
.slide-leave-to {
  right: -350px;
}
.slide-enter-to,
.slide-leave-from {
  right: 0;
}
@media only screen and (max-width: 767.5px) {
  .side-container {
    max-width: 75%;
  }
}
</style>
