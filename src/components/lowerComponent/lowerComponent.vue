<template>
  <div id="lowerPart">
    <div class="container">
      <div class="d-flex align-center flex-wrap">
        <h2 class="section-title">Pick your trip</h2>
        <p class="sub-title">
          Our team put together some trips to you to discover, feel free to
          discover each of them.
        </p>
      </div>
      <tabs :trips="myTrips" @sendActiveTrip="setCurrentTrip($event)" />
      <div class="trip-card d-flex space-between">
        <div class="img-container">
          <img :src="getImgUrl(currentTrip.images[index].imageName)" alt="" />
          <div class="buttons-container d-flex">
            <button
              aria-label="arrow left"
              @click="changeSlide('prev')"
              class="img-controllers arrow-left"
            ></button>
            <button
              aria-label="arrow right"
              @click="changeSlide('next')"
              class="img-controllers arrow-right"
            ></button>
          </div>
          <div class="img-brief d-flex flex-column">
            <span class="img-number">{{
              currentTrip.images[index].imageNumber
            }}</span>
            <span class="img-title">{{
              currentTrip.images[index].imageTitle
            }}</span>
          </div>
        </div>
        <div class="info-container">
          <h3 class="trip-title">{{ currentTrip.tripName }}</h3>
          <p class="trip-description">
            <b> {{ currentTrip.tripDescription1 }}</b>
          </p>
          <br />
          <p class="trip-description">
            {{ currentTrip.tripDescription2 }}
          </p>
          <c-button
            buttonText="SEE OUR LATEST OFFER"
            cStyle="font-size:14px;margin-top:45px"
          />
        </div>
      </div>
      <share-icons cClass="horizontal" :showText="true" />
    </div>
  </div>
</template>

<script>
import cButton from "../button/button.vue";
import ShareIcons from "../share-icons/share-icons.vue";
import tabs from "../tabs/tabs.vue";

import json from "../../trips.json";

export default {
  components: {
    cButton,
    ShareIcons,
    tabs,
  },
  data() {
    return {
      myTrips: json,
      index: 0,
      currentTrip: {
        id: 0,
        tripName: "Chill Adventure",
        tripDescription1:
          "Ornare vivamus molestie pellentesque nunc. Sed sapien erat ultrices curabitur. Erat id fringilla arcu condimentum fames.",
        tripDescription2:
          "Aliquet dictum aliquet faucibus cursus turpis. Suspendisse cum rutrum sit ut sociis. Pellentesque neque orci adipiscing pharetra lacus, dignissim pharetra ipsum blandit. Feugiat quis quam consectetur lectus id quis tortor vel, mattis.",
        images: [
          {
            imageName: "dummy-1.png",
            imageTitle: "GRAND DUNES LANDSCAPE",
            imageNumber: "01.",
          },
          {
            imageName: "dummy-2.jpg",
            imageTitle: "GRAND DUNES LANDSCAPE",
            imageNumber: "02.",
          },
        ],
      },
    };
  },
  methods: {
    setCurrentTrip(index) {
      this.currentTrip !== this.myTrips[index] ? (this.index = 0) : "";
      this.currentTrip = this.myTrips[index];
    },
    getImgUrl(pic) {
      return require("../../assets/imgs/" + pic);
    },
    changeSlide(direction) {
      if (direction === "prev" && this.index > 0) {
        this.index--;
      } else if (
        direction === "next" &&
        this.index < this.currentTrip.images.length - 1
      ) {
        this.index++;
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media only screen and (min-width: 1920.5px) {
  #lowerPart::after {
    background-size: cover;
  }
}
#lowerPart {
  width: 100%;
  position: relative;
  padding-bottom: 100px;
}
#lowerPart::after {
  content: "";
  width: 100%;
  min-height: calc(100% + 260px);
  height: fill-available;
  top: 0;
  position: absolute;
  background-image: url("~@/assets/imgs/bg-lights.svg");
  display: block;
  margin-top: -260px;
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
  position: relative;
}
.sub-title::before,
.sub-title::after {
  content: "";
  position: absolute;
  left: -54px;
  top: 50%;
  width: 18px;
  height: 2px;
  background-color: #41ead4;
  border-radius: 50px;
}
.sub-title::before {
  transform: rotate(45deg);
}
.sub-title::after {
  transform: rotate(-45deg);
}

.img-container {
  max-width: 486px;
  max-height: 472px;
  width: 100%;
  position: relative;
  border-radius: 10px;
}
.img-container::after {
  content: "";

  position: absolute;
  bottom: -55px;
  left: -55px;
  width: 230px;
  height: 230px;
  background-image: url("~@/assets/imgs/dots.png");
}
.trip-card {
  max-width: 1049px;
  width: 100%;
}
.img-container img {
  width: 100%;
  height: 100%;
  z-index: 2;
  position: relative;
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
.buttons-container {
  position: absolute;
  bottom: 0;
  right: 0;
}
.img-controllers {
  width: 65px;
  height: 65px;
  display: inline-block;
  z-index: 3;
  border: 0;
  background: #011627;
  box-shadow: -10px 14px 24px rgba(1, 22, 39, 0.08);
}
.img-controllers:hover {
  cursor: pointer;
}
.img-controllers.arrow-right,
.img-controllers.arrow-left {
  background-image: url("~@/assets/imgs/arrow.svg");
  background-repeat: no-repeat;
  background-position: center;
  transition: all 0.1s;
}
.img-controllers.arrow-left {
  transform: rotate(180deg);
  border-left: 2px solid rgba(19, 49, 73, 0.5);
  border-bottom-right-radius: 12px;
}
@media only screen and (min-width: 1024px) {
  .img-controllers.arrow-right:hover,
  .img-controllers.arrow-left:hover {
    background-position-x: 24px;
  }
}
.img-brief {
  position: absolute;
  top: 50%;
  left: -50%;
  transform: translate(75%, -50%);
  z-index: 3;
}
.img-brief::before {
  content: "";
  position: absolute;
  width: 172px;
  height: 12px;
  border-top: 2px solid #41ead4;
  border-left: 2px solid #41ead4;
  margin-top: -16px;
}
.img-number {
  font-weight: 800;
  font-size: 24px;
  line-height: 150%;
  letter-spacing: 0.15em;
  color: #41ead4;
}
.img-title {
  display: inline-block;
  max-width: 215px;
  font-weight: bold;
  font-size: 24px;
  line-height: 150%;
  letter-spacing: 0.15em;
}
@media only screen and (max-width: 1440px) {
  .trip-card {
    justify-content: center;
    max-width: 100%;
  }
  .img-container {
    margin-right: 75px;
    max-width: 375px;
  }
  .trip-title {
    font-size: 40px;
  }
}
@media only screen and (max-width: 1024px) {
  .trip-card {
    flex-direction: column;
    align-items: center;
  }
  .img-container {
    margin-right: 0;
  }
  .section-title {
    margin: 0 0 10px 0;
    font-size: 56px;
    width: 100%;
  }
  .sub-title {
    margin-left: auto;
  }
  .sub-title::before,
  .sub-title::after {
    display: none;
  }
  .info-container {
    margin-top: 56px;
  }
  .buttons-container {
    bottom: 4px;
  }
  .img-controllers {
    width: 48px;
    height: 48px;
  }
}
@media only screen and (max-width: 767.5px) {
  #lowerPart {
    background-size: cover;
    padding-bottom: 50px;
  }
  .img-number,
  .img-title {
    font-size: 16px;
  }
  .img-brief {
    transform: translate(0, -50%);
    margin-left: 43%;
  }
  .img-brief::before {
    width: 95px;
    height: 6px;
    margin-top: -8px;
  }
  .img-container::after {
    width: 115px;
    height: 115px;
    left: -51px;
  }
}
@media only screen and (max-width: 450px) {
  .info-container .btn {
    display: block;
  }
  .img-container {
    max-width: 90%;
  }
  .section-title {
    font-size: 48px;
  }
}
</style>
