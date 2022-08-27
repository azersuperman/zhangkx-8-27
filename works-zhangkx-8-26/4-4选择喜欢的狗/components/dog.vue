<template>
  <div class="my_div">
    <img :src="dogUrl" />
    <p @click="style()" :style="{ backgroundColor: colorNb }">
      {{ dogName }}
    </p>
  </div>
</template>

<script>
export default {
  props: ["index", "dogUrl", "dogName"],
  data() {
    return {
      colorNb: 1,
    };
  },
  methods: {
    style() {
      this.colorNb = `rgb(${Math.floor(Math.random() * 255)},${Math.floor(
        Math.random() * 255
      )},${Math.floor(Math.random() * 255)})`;
      this.$emit("selDog", this.dogName);
    },
  },
};
</script>

<style>
.my_div {
  width: 200px;
  border: 1px solid black;
  text-align: center;
  float: left;
}

.my_div img {
  width: 100%;
  height: 200px;
}
</style>
