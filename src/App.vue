<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Задача 1: Каждый элемент массива в своем div -->
		<div v-for="item in items" :key="item">{{ item }}</div>

		<!-- Задача 2: Квадрат каждого элемента массива в своем div -->
		<div v-for="item in items" :key="item">{{ item * item }}</div>

		<!-- Задача 3: Элементы массива в виде списка ul -->
		<ul>
			<li v-for="item in items" :key="item">{{ item }}</li>
		</ul>
	</div>
</template>

<script>
export default {
	data() {
		return {
			items: [1, 2, 3, 4, 5],
		}
	},
}
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
