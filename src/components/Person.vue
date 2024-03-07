<template>
  <div class="person">
    <h2>姓名: {{ name }} </h2>
    <h2>年龄: {{ age }}</h2>
    <button @click="changeName">修改姓名</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">显示电话号</button>
    <h2>{{ a }}</h2>
  </div>
</template>

<!--setup语法糖自动return返回数据,不必每次修改完数据都再去写return-->
<!--两个script中使用相同的lang,不写默认为js-->
<script lang="ts" setup name="Person">
// 响应式必备
import {ref} from 'vue';

let a = '888888';
// 响应式
let name = ref('张三');
let age = ref(18);
let tel = '23456665';


function changeName() {
  // 在script里面需要.value, 在template会自动解析
  name.value = '李四';
  console.log(name);

}

function changeAge() {
  age.value += 1;
  console.log(age);
}

function showTel() {
  alert(tel);
}


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
