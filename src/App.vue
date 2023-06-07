<template>
  <div id="app">
    <h1>Search Vue.js</h1>
    <input
      class="input"
      name="text"
      type="search"
      placeholder="Search..."
      v-model="query"
    /><br /><br />

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
  "Даниил на завтрак - топ",
  "адмирал",
  "барон",
  "великан",
  "герой",
  "дирижабль",
  "ежевика",
  "жираф",
  "зебра",
  "ирис",
  "йогурт",
  "король",
  "лес",
  "мандарин",
  "носорог",
  "облако",
  "паук",
  "рыцарь",
  "солнце",
  "тюльпан",
  "улитка",
  "фламинго",
  "хомяк",
  "цветок",
  "шарик",
  "щавель",
  "электрон",
  "юный",
  "яблоко",
  "автомобиль",
  "банан",
  "вишня",
  "гном",
  "дом",
  "ежик",
  "жук",
  "загадка",
  "изюм",
  "кот",
  "луна",
  "метеор",
  "ночь",
  "образ",
  "подсолнух",
  "рельсы",
  "сапог",
  "танец",
  "узел",
  "фонарь",
  "холм",
  "цепочка",
  "шоколад",
  "щенок",
  "эльф",
  "юмор",
  "яйцо",
  "авокадо",
  "бульдозер",
  "велосипед",
  "гроздь",
  "дракон",
  "ежемесячник",
  "жара",
  "затмение",
  "измерение",
  "кабан",
  "лестница",
  "муравей",
  "носок",
  "обезьяна",
  "палочка",
  "ромашка",
  "самолет",
  "творог",
  "уголь",
  "флейта",
  "хирург",
  "цирк",
  "шапка",
  "щит",
  "экран",
  "юрист",
  "ядро",
  "агентство",
  "бегемот",
  "выходной",
  "газель",
  "достопримечательность",
  "ежедневник",
  "железо",
  "зуб",
  "испытание",
  "канистра",
  "лук",
  "молния",
  "ножницы",
  "окно",
  "парус",
  "результат",
  "свет",
  "телефон",
  "удочка",
  "фехтование",
  "храм",
  "церковь",
  "шашлык",
  "щека",
  "эксперимент",
  "юность",
  "яхта"
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
  transition: 0.1s;
  transition-property: box-shadow;
}
</style>