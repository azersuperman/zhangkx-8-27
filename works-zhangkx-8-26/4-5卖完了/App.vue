<template>
  <div>
    <table>
      <!-- 2. 使用tr组件, 传入需要的数据 -->
      <tr
        is="Fruit"
        v-for="(item, index) in goodsArr"
        :key="index"
        :obj="item"
        :index="index"
      ></tr>
      <span>{{ sum }}</span>
    </table>
  </div>
</template>

<script>
import Fruit from "./components/Fruit";
export default {
  data() {
    return {
      goodsArr: [
        {
          count: 0,
          goodsName: "Watermelon",
        },
        {
          count: 0,
          goodsName: "Banana",
        },
        {
          count: 0,
          goodsName: "Orange",
        },
        {
          count: 0,
          goodsName: "Pineapple",
        },
        {
          count: 0,
          goodsName: "Strawberry",
        },
      ],
    };
  },
  components: {
    Fruit,
  },
  computed: {
    sum() {
      return this.goodsArr.reduce((sum, b) => (sum += b.count), 0);
    },
  },
};
</script>

<style></style>
