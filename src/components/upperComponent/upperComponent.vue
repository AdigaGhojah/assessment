<template>
  <div id="upperPart">
    <div class="container">
      <!-- Start Header -->
      <cHeader />
      <!-- End Header -->
      <!-- Start Main Text -->
      <section class="main-text d-flex align-center flex-column">
        <h1>Night Trips</h1>
        <span class="d-block sub-title"
          >WE GOT TRIPS FOR THE TRIPPSTER IN YOU</span
        >
        <p class="brief">
          Neque, eros commodo, nascetur ullamcorper vitae. Tincidunt ut
          venenatis, volutpat lorem ut faucibus mauris, quisque. Integer gravida
          sed quis congue. Vel risus, arcu a viverra leo id pulvinar ultricies.
          Enim in in in pulvinar nulla sollicitudin. Ullamcorper.
        </p>
      </section>
      <!-- End Main Text -->
      <shareIcons cClass="flex-column space-bottom"/>
      <span class="scroll">SCROLL</span>
    </div>
  </div>
</template>

<script>
import cHeader from "../header/header.vue";
import shareIcons from "../share-icons/share-icons.vue";
export default {
  props: {
    msg: String,
  },
  components: {
    cHeader,
    shareIcons,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media only screen and (min-width: 1920.5px) {
  #upperPart {
    background-size: contain;
  }
}
#upperPart {
  background-image: url("~@/assets/imgs/background.png");
  background-repeat: no-repeat;
  width: 100%;
  height: calc(100vh + 232px);
  position: relative;
}
#upperPart::after {
  content: "";
  position: absolute;
  width: 100%;
  max-height: 378px;
  bottom: 0;
  height: 100%;

  background: linear-gradient(
    180deg,
    rgba(1, 22, 39, 0) 0%,
    #011627 76.64%,
    #011627 100%
  );
}

.container {
  max-width: 1413px;
  height: 100%;
  padding: 0 15px;
  margin: 0 auto;
  position: relative;
}

.main-text {
  height: calc(100% - 419px);
  padding-top: 152px;
  text-align: center;
}
h1 {
  font-family: "Noe Display";
  font-size: 120px;
  line-height: 153px;
  letter-spacing: -0.02em;
  margin: 0 0 16px;

}
.sub-title {
  font-weight: bold;
  font-size: 18px;
  line-height: 24px;
  /* identical to box height */
  letter-spacing: 0.1em;

  margin-bottom: 50px;
}
.brief {
  max-width: 643px;
  font-size: 17px;
  line-height: 150%;
  margin: 0;

}
.scroll {
  /* bottom: 16px; */
  bottom: 256px;
  left: -24px;
  font-size: 15px;
  line-height: 190%;
  transform: rotate(-90deg);
  display: inline-block;
  letter-spacing: 0.05em;
  z-index: 1;

  position: relative;
}
.scroll::after {
  content: "";
  bottom: -27px;
  left: -52px;
  transform: rotate(-90deg);

  position: absolute;
  width: 2px;
  height: 80px;

  background: linear-gradient(180deg, #09f4f4 0%, #00c9e0 100%);
  border-radius: 13px;
}

@media only screen and (max-width: 767.5px) {
  #upperPart {
    background-position: center;
  }
  .main-text {
    height: calc(100% - (82px + 100px + 100px));
    padding-top: 100px;
  }

  h1 {
    font-size: 56px;
    line-height: 1.5;
  }
  .sub-title {
    font-size: 18px;
    line-height: 1.5;
    margin-bottom: 32px;
  }
  .brief {
    font-size: 14px;
  }
  .scroll {
    bottom: 6px;
    left: -16px;
  }
  .scroll::after {
    bottom: -6px;
    left: -28px;
    height: 40px;
  }

}
</style>
