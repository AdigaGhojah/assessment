<template>
  <div id="lowerPart">
    <div class="container">
      <div class="d-flex align-center">
        <h3 class="section-title">Pick your trip</h3>
        <p class="sub-title">
          Our team put together some trips to you to discover, feel free to
          discover each of them.
        </p>
      </div>
      <ul class="tabs d-flex space-between">
        <li class="tab active">Chill Adventure</li>
        <li class="tab">Spooky Times</li>
        <li class="tab">Desert Madness</li>
        <li class="tab">Out in the wild</li>
      </ul>
      <div class="trip-card d-flex space-between">
        <div class="img-container">
          <img src="@/assets/imgs/dummy-1.png" alt="" />
        </div>
        <div class="info-container">
          <h2 class="trip-title">Chill Adventure</h2>
          <p class="trip-description">
            <b>
              Ornare vivamus molestie pellentesque nunc. Sed sapien erat
              ultrices curabitur. Erat id fringilla arcu condimentum fames.</b
            >
          </p>
          <br />
          <p class="trip-description">
            Aliquet dictum aliquet faucibus cursus turpis. Suspendisse cum
            rutrum sit ut sociis. Pellentesque neque orci adipiscing pharetra
            lacus, dignissim pharetra ipsum blandit. Feugiat quis quam
            consectetur lectus id quis tortor vel, mattis.
          </p>
          <c-button buttonText="SEE OUR LATEST OFFER" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import cButton from "../button/button.vue";
export default {
  components: {
    cButton,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#lowerPart {
  width: 100%;
  position: relative;
  padding-bottom: 100px;
}
#lowerPart::after {
  content: "";
  width: 100%;
  min-height: calc(100% + 280px);
  height: fill-available;
  top: 0;
  position: absolute;
  /* background-image: url(/img/bg-lights.a643be40.svg); */
  background-image: url("~@/assets/imgs/bg-lights.svg");
  display: block;
  margin-top: -280px;
}
.container {
  margin: 0 auto;
  max-width: 1230px;
  padding: 0 15px;
  z-index: 1;
  position: relative;
}
.section-title {
  margin: 0 90px 10px 0;
  font-family: "Noe Display";
  font-size: 72px;
  line-height: 110%;
  letter-spacing: -0.02em;
}
.sub-title {
  max-width: 349px;
  width: 100%;
  font-family: "Larsseit";
  font-size: 16px;
  line-height: 150%;
  letter-spacing: -0.02em;
}
.tabs {
  border-bottom: 2px solid rgba(65, 234, 212, 0.3);
  width: 100%;
  margin: 83px 0 130px;
  list-style-type: none;
  padding-left: 0;
}
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
.img-container {
  max-width: 486px;
  width: 100%;
}
.trip-card {
  max-width: 1049px;
  width: 100%;
}
.img-container img {
  width: 100%;
}
.info-container {
  max-width: 439px;
  width: 100%;
}
.trip-title {
  font-family: "Noe Display";
  font-size: 65px;
  line-height: 110%;
  letter-spacing: -0.02em;
}
.trip-description {
  font-family: "Larsseit";
  font-size: 17px;
  line-height: 150%;
  letter-spacing: -0.02em;
  margin: 0;
}
</style>
