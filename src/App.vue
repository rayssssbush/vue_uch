<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <div>
    <!-- №1: Формируем верстку с <div> и <p>, включая <p class="divider"> -->
    <div v-for="item in items" :key="item">
      <p>{{ item }}</p>
      <p class="divider"></p>
    </div>

    <!-- №2: Формируем верстку с <ul> и <li>, включая <li class="divider"> -->
    <ul>
      <li v-for="(item, index) in items" :key="item">
        {{ item }}
        <!-- Добавляем divider после каждого элемента, кроме последнего -->
        <li v-if="index < items.length - 1" class="divider"></li>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [1, 2, 3],
    };
  },
};
</script>


<style scoped>
#app {
	text-align: center;
	background-color: #fff;
	padding: 20px;
	border-radius: 8px;
	box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
	max-width: 300px;
	width: 100%;
}

div {
	font-size: 20px;
	color: #333;
	margin: 10px 0;
	padding: 10px;
	background-color: #e1f5fe;
	border-radius: 5px;
	box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}

div:first-child {
	background-color: #b3e5fc;
}

div:last-child {
	background-color: #81d4fa;
}
</style>
