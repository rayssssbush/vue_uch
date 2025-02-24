<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>
<template>
	<div>
		<!-- Кнопки для вывода квадратов чисел -->
		<button @click="showSquare(2)">Квадрат числа 2</button>
		<button @click="showSquare(3)">Квадрат числа 3</button>
	</div>
</template>

<script>
export default {
	methods: {
		// Метод для вывода квадрата числа через alert
		showSquare(number) {
			alert(`Квадрат числа ${number}: ${number * number}`)
		},
	},
}
</script>

<style scoped>
/* Стили по желанию */
button {
	padding: 10px 20px;
	background-color: #4caf50;
	color: white;
	border: none;
	cursor: pointer;
	margin: 5px;
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
