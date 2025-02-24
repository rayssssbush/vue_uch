<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>
<template>
	<div>
		<!-- Ссылка с обработчиком клика, отменяющим переход -->
		<a href="https://example.com" @click.prevent="handleLinkClick"
			>Кликни меня, но не перейдешь!</a
		>

		<!-- Кнопка с обработчиком клика, срабатывающим только один раз -->
		<button @click="handleButtonClick" :disabled="buttonClicked">
			Нажми меня (срабатывает только один раз)
		</button>
	</div>
</template>

<script>
export default {
	data() {
		return {
			buttonClicked: false, // Флаг, чтобы отслеживать, был ли клик по кнопке
		}
	},
	methods: {
		// Обработчик клика по ссылке, предотвращающий переход
		handleLinkClick(event) {
			console.log('Ссылка была кликнута, но переход не произошел.')
			// Если необходимо, можно добавить дополнительную логику обработки
		},

		// Обработчик клика по кнопке, срабатывающий только один раз
		handleButtonClick() {
			if (!this.buttonClicked) {
				console.log('Кнопка была кликнута!')
				this.buttonClicked = true // Останавливаем дальнейшие клики
			}
		},
	},
}
</script>

<style scoped>
a {
	color: #4caf50;
	text-decoration: none;
}

button {
	padding: 10px 20px;
	background-color: #4caf50;
	color: white;
	border: none;
	cursor: pointer;
	margin-top: 20px;
}

button:disabled {
	background-color: #cccccc;
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
