<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<p>Квадрат числа: {{ num * num }}</p>
		<p>Сумма чисел: {{ num1 + num2 + num3 }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			num: 5,
			num1: 1,
			num2: 2,
			num3: 3,
		}
	},
}
</script>

<style scoped>
/* Стили по желанию */
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
