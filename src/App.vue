<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>
<template>
	<div>
		<!-- Абзац для вывода содержимого свойства text -->
		<p>{{ text }}</p>

		<!-- Кнопки для изменения значения text -->
		<button @click="changeText('Первое значение')">Первое значение</button>
		<button @click="changeText('Второе значение')">Второе значение</button>
	</div>
</template>

<script>
export default {
	data() {
		return {
			text: 'Начальное значение', // Исходное значение свойства text
		}
	},
	methods: {
		// Метод для изменения значения text
		changeText(newText) {
			this.text = newText
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
