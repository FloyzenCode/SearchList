<template>
  <div id="app">
    <h1>Search Vue.js</h1>
    <input class="input" name="text" type="search" placeholder="Search..." v-model="query" /><br /><br />

    <!--{{ queryReverse }} or {{ query }}-->

    <ul>
      <li v-for="product in queryProducts" :key="product">
        {{ product }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const products = ref([
  "Яблоки",
  "Хлеб",
  "Бананы",
  "Молоко",
  "Сметана",
  "Шоколад",
  "Снеки",
]);

const query = ref("");

const queryProducts = computed(() => {
  const queryVal = query.value.toLowerCase();
  return products.value.filter(
    (product) => product.toLowerCase().indexOf(queryVal) !== -1
  );
});


const queryReverse = computed(() => {
  return query.value.split("").reverse().join("");
});
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  marker: none;
  list-style-type: none;
}

body {
  background: black;
}

#app {
  align-items: center;
  text-align: center;
  justify-content: center;
  margin-top: 60px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

h1 {
  color: #fff;
  margin-bottom: 100px;
}

ul {
  background: white;
}

.input {
  background-color: #212121;
  max-width: 190px;
  height: 40px;
  padding: 10px;
  /* text-align: center; */
  border: 2px solid white;
  border-radius: 5px;
  /* box-shadow: 3px 3px 2px rgb(249, 255, 85); */
}

.input:focus {
  color: rgb(0, 255, 255);
  background-color: #212121;
  outline-color: rgb(0, 255, 255);
  box-shadow: -3px -3px 15px rgb(0, 255, 255);
  transition: .1s;
  transition-property: box-shadow;
}
</style>