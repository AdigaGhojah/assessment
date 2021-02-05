<template>
  <ul class="tabs d-flex space-between">
    <li
      class="tab"
      :class="{ active: currentActive === index }"
      @click="activeTab(index)"
      v-for="(trip, index) in trips"
      :key="trip.id"
    >
      {{ trip.tripName }}
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    trips: Array,
  },
  data() {
    return {
      currentActive: 0,
    };
  },
  methods: {
    activeTab(index) {
      this.currentActive = index;
      this.$emit('sendActiveTrip',index)
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.tab {
  max-width: 282px;
  width: 100%;
  font-weight: bold;
  font-size: 16px;
  line-height: 110%;
  text-align: center;
  letter-spacing: 0.08em;
  color: #fff;
  opacity: 0.5;
  padding-bottom: 37px;
}
.tab:hover {
  cursor: pointer;
  color: #41ead4;
  opacity: 1;
}
.tab.active {
  color: #41ead4;
  opacity: 1;
  border-bottom: 4px solid #41ead4;
}
@media only screen and (max-width: 767.5px) {
  .tabs {
    margin: 40px 0 75px;
  }
  .tab {
    padding-bottom: 16px;
  }
  .tab {
    letter-spacing: normal;
    font-size: 16px;
    font-weight: normal;
  }
}
</style>
