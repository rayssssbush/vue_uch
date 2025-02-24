<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Применяем динамические классы в зависимости от значений isValid и isDisabled -->
		<p :class="{ valid: isValid, disabled: isDisabled }">
			Текст с динамическими классами.
		</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			isValid: true, // Если true, добавится класс 'valid'
			isDisabled: true, // Если true, добавится класс 'disabled'
		}
	},
}
</script>

<style scoped>
/* Стили для классов */
.valid {
	color: green;
}
.disabled {
	color: gray;
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
