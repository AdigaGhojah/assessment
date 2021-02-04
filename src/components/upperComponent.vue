<template>
  <div id="upperPart">
    <!-- <h1>{{ msg }}</h1> -->
    <!-- Start Header -->
    <div class="container">
      <header class="d-flex align-center space-between">
        <!-- Start Logo -->
        <a href="/" title="logo">
          <img src="@/assets/imgs/logo.svg" alt="logo" />
        </a>
        <!-- End Logo -->
        <!-- Start Header Right Side-->
        <div class="d-flex align-center">
          <button class="search-button">
            <img src="@/assets/imgs/search-icon.svg" alt="search-icon" />
          </button>
          <button class="menu-btn">MENU</button>
        </div>
        <!-- End Header Right Side-->
      </header>
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

      <div class="share-page d-flex flex-column align-center">
        <a href="#" title="twitter"
          ><img src="@/assets/imgs/twitter.svg" alt="twitter"
        /></a>
        <a href="#" title="instagram"><span class="instagram"></span></a>
        <a href="#" title="facebook"
          ><img src="@/assets/imgs/facebook.svg" alt="facebook"
        /></a>
      </div>
      <span class="scroll">SCROLL</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#upperPart {
  background-image: url("~@/assets/imgs/background.png");
  background-repeat: no-repeat;
  width: 100%;
  height: 100vh;
}
header {
  padding-top: 77px;
  padding-right: 9px;
}
.container {
  max-width: 1413px;
  height: 100%;
  padding: 0 15px;
  margin: 0 auto;
  position: relative;
}
.search-button {
  cursor: pointer;
  margin-right: 35px;
  width: 32px;
  height: 32px;
  padding: 8px;
  border-radius: 50%;
  border: 0;
  background-color: transparent;
  transition: all 0.3s;
}
.search-button:hover {
  width: 35px;
  height: 35px;
  background-color: rgba(110, 110, 110, 0.5);
}
.menu-btn {
  border: 0;
  cursor: pointer;
  width: 167px;
  font-family: Larsseit;
  font-weight: bold;
  font-size: 16px;
  line-height: 60px;

  letter-spacing: 0.1em;
  color: #fff;

  background-color: #00c9e0;
  /* Button Shadow */

  box-shadow: 5px 15px 40px rgba(0, 201, 224, 0.2);
  border-radius: 48px;
  text-align: center;
  position: relative;
  transition: background-color 0.3s;
}
.menu-btn:hover {
  background-color: #00b0c4;
}
.menu-btn:hover::after {
  right: 0;
}
.menu-btn::after {
  content: "";
  position: absolute;
  width: 30px;
  height: 2px;
  top: 50%;
  margin-top: -1px;
  right: -15px;
  transition: right 0.3s;
  background-color: #fff;
  border-radius: 16px;
}
.main-text {
  height: calc(100% - 419px);
  padding-top: 152px;
  text-align: center;
}
h1 {
  font-family: Noe Display;
  font-size: 120px;
  line-height: 153px;
  letter-spacing: -0.02em;
  margin: 0 0 16px;
  color: #fff;
}
.sub-title {
  font-family: Larsseit;
  font-weight: bold;
  font-size: 18px;
  line-height: 24px;
  /* identical to box height */

  letter-spacing: 0.1em;

  color: #fff;
  margin-bottom: 50px;
}
.brief {
  max-width: 643px;
  font-family: Larsseit;
  font-size: 17px;
  line-height: 150%;
  margin: 0;

  color: #fff;
}
.scroll {
  bottom: 16px;
  left: -24px;

  font-family: Larsseit;
  font-weight: bold;
  font-size: 15px;
  line-height: 190%;
  transform: rotate(-90deg);
  display: inline-block;
  letter-spacing: 0.05em;

  color: #fff;
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
.share-page {
  /* margin-right: 0;
  width: fit-content;
  margin-left: auto; */
  position: absolute;
  right: 0;
}
.instagram {
  margin: 18px 0;
  display: inline-block;
  position: relative;
  width: 20px;
  height: 20px;
}
.instagram::before {
  content: "";

  width: 20px;
  height: 20px;
  display: inline-block;
  position: absolute;
  border-radius: 4px;
  right: 0;
  top: 0;
  border: 2px solid #41ead4;
}
.instagram::after {
  content: "";
  border-radius: 50%;
  position: absolute;
  width: 8px;
  height: 8px;
  right: 50%;
  top: 50%;
  margin-right: -4px;
  margin-top: -4px;
  display: inline-block;

  border: 2px solid #41ead4;
}
@media only screen and (max-width: 767.5px) {
  #upperPart {
background-position: center;
}
  header {
    padding-top: 32px;
    padding-right: 0px;
  }
  .search-button {
    margin-right: 16px;
  }
  .menu-btn {
    width: 90px;
    font-size: 14px;
    line-height: 48px;
    border-radius: 24px;
  }
  .menu-btn::after {
    width: 16px;
    right: -8px;
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
  .share-page {
    bottom: 5px;
    right:16px;
  }
}
</style>
