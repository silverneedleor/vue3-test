<template>
  <div class="person">
    <h2>这辆车的品牌是{{ car.brand }}, 价值是{{ car.price }}w</h2>
    <button @click="changePrice">修改价格</button>
    <h2>游戏列表: </h2>
    <ul>
      <li v-for="g in games" :key="g.id">{{g.name}}</li>
    </ul>
    <button @click="changeFirstGame">修改第一个游戏的名字</button>
  </div>
</template>

<!--setup语法糖自动return返回数据,不必每次修改完数据都再去写return-->
<!--两个script中使用相同的lang,不写默认为js-->
<script lang="ts" setup name="Person">
import {reactive} from "vue";

let car = reactive({brand: '奔驰', price: 100});



console.log(car);
console.log(Proxy);

let games = reactive([
    {id: '123456781',name:'王者荣耀'},
    {id: '123456782',name:'原神'},
    {id: '123456783',name:'三国志'}
])



function changePrice() {
  car.price += 10;
  console.log(car.price);
}

function changeFirstGame() {
  games[0].name = '吃鸡游戏';
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
