<template>
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
      <c-button @openMenu="openMenu" buttonText="MENU"/>
    </div>
    <!-- End Header Right Side-->
  </header>
</template>

<script>
import cButton from "../button/button.vue";
export default {
    components: {
    cButton,
  },
  methods:{
    openMenu(){
      this.$emit("openMenu");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  padding-top: 77px;
  padding-right: 9px;
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
  background-color: #00c9e0;
  font-family: "Larsseit";
  color: #fff;
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
@media only screen and (max-width: 767.5px) {
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
}
</style>
