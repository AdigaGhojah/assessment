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
      <shareIcons cClass="flex-column space-bottom" />
      <span v-show="!scrolled" class="scroll">SCROLL</span>
    </div>
  </div>
</template>

<script>
import cHeader from "../header/header.vue";
import shareIcons from "../share-icons/share-icons.vue";
export default {
  components: {
    cHeader,
    shareIcons,
  },
  data() {
    return {
      limitPosition: 50,
      scrolled: false,
      lastPosition: 0,
    };
  },
  methods: {
    handleScroll() {
      if (
        this.lastPosition < window.scrollY &&
        this.limitPosition < window.scrollY
      ) {
        this.scrolled = true;
      }

      if (
        this.lastPosition > window.scrollY &&
        this.limitPosition > window.scrollY
      ) {
        this.scrolled = false;
      }

      this.lastPosition = window.scrollY;
    },
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
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
@media only screen and (min-width: 768px) {
  #upperPart {
    background-image: url("~@/assets/imgs/background.webp");
  }
}
#upperPart {
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
  /* animation: animation 1s infinite; */
  position: relative;
}
/* @keyframes animation {
  0% {
    bottom: 256px;
  }
  50% {
    bottom: 265px;
  }
  100% {
    bottom: 256px;
  }
} */
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
    background-image: url("~@/assets/imgs/mobile-background.webp");
    background-position: center;
    height: calc(100vh + 50px);
  }
  #upperPart::after {
    max-height: 150px;
  }
  .main-text {
    height: calc(100% - (82px + 40px + 100px));
    padding-top: 50px;
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
    left: -16px;
  }
  .scroll::after {
    bottom: -6px;
    left: -28px;
    height: 40px;
  }
  /* @keyframes animation {
    0% {
      bottom: 50px;
    }
    50% {
      bottom: 65px;
    }
    100% {
      bottom: 50px;
    }
  } */
}
</style>
