<template>
  <div>
    <span>{{ obj.shopName }}</span>
    <button @click="addNum(index)">+</button>
    <span>{{ obj.count }}</span>
    <button>-</button>
  </div>
</template>

<script>
export default {
  props: ["obj", "index"],
  methods: {
    addNum(index) {
      this.$emit("comSum", index, 1);
    },
  },
};
</script>

<style></style>
