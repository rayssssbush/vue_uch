<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Инпут для текста -->
		<input v-model="inputText" placeholder="Введите текст" />
		<p>{{ inputText }}</p>

		<!-- Инпут для текста, вывод в верхнем регистре -->
		<input
			v-model="inputTextUpperCase"
			placeholder="Введите текст для верхнего регистра"
		/>
		<p>{{ inputTextUpperCase.toUpperCase() }}</p>

		<!-- Инпут для числа, вывод квадрата числа -->
		<input
			v-model.number="inputNumber"
			type="number"
			placeholder="Введите число"
		/>
		<p>{{ inputNumber ** 2 }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			inputText: '',
			inputTextUpperCase: '',
			inputNumber: 0,
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
