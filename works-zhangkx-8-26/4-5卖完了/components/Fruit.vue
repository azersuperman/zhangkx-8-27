<template>
  <div>
    <table>
      <tr>
        <td>
          <input type="text" v-model.trim.number="obj.count" />
        </td>
        <td>
          <span>{{ obj.goodsName }}</span>
        </td>
        <td>{{ write }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  props: ["obj"],
  computed: {
    write() {
      if (this.obj.count === 0) return "εεδΊ!!!";
    },
  },
};
</script>

<style></style>
