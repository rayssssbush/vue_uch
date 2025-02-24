<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Задача 1: Инпут и вывод текста при нажатии Enter -->
		<input
			v-model="inputText"
			@keyup.enter="displayText"
			placeholder="Введите текст"
		/>
		<p>{{ displayedText }}</p>

		<!-- Задача 2: Ссылка с проверкой нажатия Ctrl -->
		<a href="#" @click="handleLinkClick">Нажмите на ссылку с зажатым Ctrl</a>
		<p>{{ linkMessage }}</p>

		<!-- Задача 3: Ссылка с различными действиями на кнопки мыши -->
		<a
			href="#"
			@mousedown.left="mouseClick('left')"
			@mousedown.right="mouseClick('right')"
			@mousedown.middle="mouseClick('middle')"
			>Нажмите на ссылку</a
		>
		<p>{{ mouseMessage }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			inputText: '', // Для хранения текста из инпута
			displayedText: '', // Для отображения текста при нажатии Enter
			linkMessage: '', // Сообщение для ссылки с Ctrl
			mouseMessage: '', // Сообщение для мышиных кнопок
		}
	},
	methods: {
		// Задача 1: Отображаем введенный текст при нажатии Enter
		displayText() {
			this.displayedText = this.inputText
		},

		// Задача 2: Проверка нажатия на ссылку с зажатым Ctrl
		handleLinkClick(event) {
			if (event.ctrlKey) {
				this.linkMessage = 'Ctrl клавиша зажата!'
			} else {
				this.linkMessage = 'Ctrl клавиша не зажата'
			}
		},

		// Задача 3: Определение какой кнопкой мыши был совершен клик
		mouseClick(button) {
			this.mouseMessage = button
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
