<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="obj.name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim.number="obj.age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="obj.sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addInfo">添加/修改</button>
    </div>
    <div>
      <table
        border="1"
        cellpadding="10"
        cellspacing="0"
        v-show="arr.length != 0"
      >
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="delInfo">删除</button>
            <button @click="editor(item, index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      arr: [
        { name: "Tom", age: 19, sex: "男" },
        { name: "Jone", age: 21, sex: "女" },
      ],
      obj: { name: "", sex: "", age: "" },
      varia: -999,
      formShow: true,
    };
  },
  methods: {
    addInfo() {
      if (this.varia === -999) {
        if (
          this.obj.name === "" ||
          this.obj.sex === "" ||
          this.obj.age === ""
        ) {
          return alert("请输入正确的值");
        }
        //因为扩展运算符(...)对对象实例的拷贝属于一种浅拷贝，这基本数据类型的拷贝会完整的复制一份；
        //当类型是引用数据Object，
        //如果拷贝的时候拷贝的是对象的引用，当原对象发生变化的时候，拷贝对象也会跟着变化
        this.arr.push({ ...this.obj });
      } else {
        this.$set(this.arr, this.varia, { ...this.obj });
        this.varia = -999;
      }
      this.obj = { name: "", sex: "", age: "" };
    },
    editor(item, index) {
      this.varia = index;
      this.obj = { ...item };
    },
    delInfo(index) {
      this.arr.splice(index, 1);
    },
  },
};
</script>
