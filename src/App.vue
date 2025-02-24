<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>
<template>
	<div>
		<!-- Абзацы, изначально скрыты -->
		<p v-if="isVisible[0]">Абзац 1</p>
		<p v-if="isVisible[1]">Абзац 2</p>
		<p v-if="isVisible[2]">Абзац 3</p>

		<!-- Кнопки для toggling абзацев -->
		<button @click="toggleVisibility(0)">
			{{ isVisible[0] ? 'Скрыть абзац 1' : 'Показать абзац 1' }}
		</button>
		<button @click="toggleVisibility(1)">
			{{ isVisible[1] ? 'Скрыть абзац 2' : 'Показать абзац 2' }}
		</button>
		<button @click="toggleVisibility(2)">
			{{ isVisible[2] ? 'Скрыть абзац 3' : 'Показать абзац 3' }}
		</button>
	</div>
</template>

<script>
export default {
	data() {
		return {
			isVisible: [false, false, false], // Массив для управления видимостью абзацев
		}
	},
	methods: {
		// Метод для переключения видимости абзаца
		toggleVisibility(index) {
			this.isVisible[index] = !this.isVisible[index]
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
	margin-top: 10px;
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
