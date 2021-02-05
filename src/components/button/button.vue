<template>
  <a class="btn">{{ buttonText }}</a>
</template>

<script>
export default {
  props: {
    buttonText: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btn {
  border: 0;
  cursor: pointer;
  /* width: 167px; */
  padding: 0 58px;
  display: inline-block;
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
.btn:hover {
  background-color: #00b0c4;
}
.btn:hover::after {
  right: 0;
}
.btn::after {
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
  .btn {
    width: 90px;
    font-size: 14px;
    line-height: 48px;
    border-radius: 24px;
  }
  .btn::after {
    width: 16px;
    right: -8px;
  }
}
</style>
