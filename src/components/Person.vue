<template>
  <div class="person">
    <h2>姓名: {{ name }} </h2>
    <h2>年龄: {{ age }}</h2>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">显示电话号</button>

  </div>
</template>

<script lang="ts">
export default {
  name: "Person",
  // 验证在vue3中setup的优先级高
  // beforeCreate() {
  //   console.log('beforeCreate')
  // },
  setup(){
  // 数据, 此时数据不是响应式的
    let name = '张三';
    let age = 18;
    let tel = '23456665';

    // 用来知道setup的this是undefined
    // console.log(this);

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
