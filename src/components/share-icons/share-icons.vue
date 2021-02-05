<template>
  <div :class="comClass" class="share-page d-flex align-center">
    <span v-if="showText">SHARE IT:</span>
    <a href="#" title="twitter"
      ><img src="@/assets/imgs/twitter.svg" alt="twitter"
    /></a>
    <a href="#" title="instagram"><span class="instagram"></span></a>
    <a href="#" title="facebook"
      ><img src="@/assets/imgs/facebook.svg" alt="facebook"
    /></a>
  </div>
</template>

<script>
export default {
  props: {
    cClass: String,
    showText: Boolean,
  },
  computed: {
    comClass() {
      return this.cClass;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
span {
  width: 100%;
  margin-bottom: 20px;
  font-weight: bold;
  font-size: 15px;
  letter-spacing: 0.15em;
}
.share-page {
  position: absolute;
  right: 0;
  bottom: 0;
  z-index: 1;
  flex-wrap: wrap;
}
.share-page.space-bottom {
  bottom: 240px;
}
.share-page.horizontal {
  right: -58px;
  bottom: 20px;
}
.share-page.horizontal::after {
  content: "";
  position: absolute;
  width: 133px;
  height: 31px;
  border-right: 2px solid #41ead4;
  border-bottom: 2px solid #41ead4;
  margin-bottom: -70px;
}
.share-page.horizontal a {
  z-index: 1;
}
.share-page.horizontal a:nth-child(2) {
  order: 3;
}
.share-page.horizontal .instagram {
  order: 1;
  margin: 0;
}
.share-page.horizontal a:last-child {
  margin: 0 30px;
  order: 2;
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

  width: 18px;
  height: 18px;
  display: inline-block;
  position: absolute;
  border-radius: 6px;
  right: 0;
  top: 0;
  border: 2px solid #41ead4;
}
.instagram::after {
  content: "";
  border-radius: 50%;
  position: absolute;
  width: 6px;
  height: 6px;
  right: 50%;
  top: 50%;
  margin-right: -4px;
  margin-top: -4px;
  display: inline-block;

  border: 2px solid #41ead4;
}
@media only screen and (max-width: 1440px) {
  span {
    text-align: right;
  }
  .share-page.horizontal {
    padding-right: 16px;
  }
  .share-page,
  .share-page.horizontal {
    right: 16px;
    justify-content: flex-end;
  }
  .share-page.horizontal::after {
    right: 0;
  }

}
@media only screen and (max-width: 767.5px) {
  .share-page {
    bottom: 5px;
  }
  .share-page.horizontal {
    position: relative;
    bottom:0;
    justify-content: center;
    margin-top:16px;
    padding-right: 0;
    right: unset;
  }
  span{
    text-align: center;
  }
  .share-page.horizontal::after {
    right:unset;
  } 
}
</style>
