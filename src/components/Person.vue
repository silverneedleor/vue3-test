<template>
  <div class="person">
    <h2>姓名: {{ name }} </h2>
    <h2>年龄: {{ age }}</h2>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">显示电话号</button>
    <button @click="b">{{a}}</button>
    <button @click="b">{{c}}</button>
  </div>
</template>

<script lang="ts">
export default {
  name: "Person",
  beforeCreate() {
    console.log('beforeCreate')
  },
  data() {
    return {
      a: 10,
      // 需要格外注意, setup的执行顺序优先,因此才能读到, 但是不能反过来
      c: this.name,
    }
  },
  methods: {
    b() {
      console.log('b')
    },
  },
  setup(){
  // 数据, 此时数据不是响应式的
    let name = '张三';
    let age = 18;
    let tel = '23456665';

    console.log(this);

    function changeName() {
      name = '李四';
      console.log(name);

    }

    function changeAge() {
      age += 1;
      console.log(age);
    }

    function showTel() {
      alert(tel);
    }


    return {name, age, changeName, changeAge, showTel};
  }
};
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}

button {
  margin: 0 5px;
  border-radius: 5px;
}
</style>
