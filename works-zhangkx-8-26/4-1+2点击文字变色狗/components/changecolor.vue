<template>
  <div class="my_div">
    <img src="https://scpic.chinaz.net/files/pic/pic9/202003/zzpic23514.jpg" />
    <p @click="style()" :style="{ backgroundColor: colorNb }">这是一个修狗</p>
  </div>
</template>

<script>
export default {
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
