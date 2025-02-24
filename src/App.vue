<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Задача 1: Вывод текста из textarea -->
		<textarea v-model="text" placeholder="Введите текст"></textarea>
		<p>{{ text }}</p>

		<!-- Задача 2: Вывод слов из textarea в виде списка -->
		<button @click="convertTextToList">Преобразовать в список</button>
		<ul>
			<li v-for="(word, index) in words" :key="index">{{ word }}</li>
		</ul>
	</div>
</template>

<script>
export default {
	data() {
		return {
			text: '',
			words: [],
		}
	},
	methods: {
		convertTextToList() {
			this.words = this.text.split(' ').filter(word => word.length > 0) // Разделяем по пробелам и фильтруем пустые слова
		},
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
