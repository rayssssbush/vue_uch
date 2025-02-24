<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>
<template>
	<div>
		<!-- Вывод полной стоимости (цена * количество) -->
		<p>Полная стоимость: {{ price }}</p>

		<!-- Кнопка для изменения стоимости продукта -->
		<button @click="changeCost(200)">Изменить цену на 200</button>
	</div>
</template>

<script>
export default {
	data() {
		return {
			cost: 100, // Начальная цена продукта
			amount: 5, // Количество продуктов
		}
	},
	computed: {
		// Вычисляемое свойство для расчета полной стоимости
		price() {
			return this.cost * this.amount
		},
	},
	methods: {
		// Метод для изменения стоимости
		changeCost(newCost) {
			this.cost = newCost
		},
	},
}
</script>

<style scoped>
button {
	padding: 10px 20px;
	background-color: #4caf50;
	color: white;
	border: none;
	cursor: pointer;
	margin-top: 20px;
}

button:hover {
	background-color: #45a049;
}
</style>

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
