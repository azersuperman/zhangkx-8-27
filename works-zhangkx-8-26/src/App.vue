<template>
  <div>
    <h2>商品清单如下</h2>
    <div v-for="(obj, index) in shopData" :key="index">
      {{ obj.shopName }} -- {{ obj.price }}元/份
    </div>
    <p>请选择购买数量:</p>
    <ShopFood
      v-for="(item, index) in shopData"
      :key="index"
      :index="index"
      :obj="item"
      @comSum="fn"
    ></ShopFood>
  </div>
</template>

<script>
import ShopFood from "./components/ShopFood.vue";
export default {
  components: {
    ShopFood,
  },
  data() {
    return {
      shopData: [
        {
          shopName: "可比克薯片",
          price: 5.5,
          count: 0,
        },
        {
          shopName: "草莓酱",
          price: 3.5,
          count: 0,
        },
        {
          shopName: "红烧肉",
          price: 55,
          count: 0,
        },
        {
          shopName: "方便面",
          price: 12,
          count: 0,
        },
      ],
    };
  },
  mothods: {
    fn(index, num) {
      console.log(1);
      // this.shopData[index].count += a;
    },
  },
};
</script>

<style></style>
