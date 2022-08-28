<template>
  <div>
    <span>{{ obj.shopName }}</span>
    <button @click="addNum(index)">+</button>
    <span>{{ obj.count }}</span>
    <button @click="redNum">-</button>
  </div>
</template>

<script>
export default {
  props: ["obj", "index"],
  methods: {
    addNum() {
      this.$emit("add", this.index);
    },
    redNum() {
      this.$emit("red", this.index);
    },
  },
};
</script>

<style></style>
