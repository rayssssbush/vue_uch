<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Задача 1: Добавление элемента в конец списка -->
		<ul>
			<li v-for="(item, index) in items" :key="index">{{ item }}</li>
		</ul>
		<input v-model="newItem" placeholder="Введите новый элемент" />
		<button @click="addItemToEnd">Добавить в конец</button>

		<!-- Задача 2: Добавление элемента в начало списка -->
		<ul>
			<li v-for="(item, index) in itemsReversed" :key="index">{{ item }}</li>
		</ul>
		<input v-model="newItem" placeholder="Введите новый элемент" />
		<button @click="addItemToStart">Добавить в начало</button>
	</div>
</template>

<script>
export default {
	data() {
		return {
			items: ['Элемент 1', 'Элемент 2', 'Элемент 3'],
			newItem: '', // Текст для добавления в список
		}
	},
	computed: {
		// Создаем вычисляемое свойство для отображения списка с элементами в обратном порядке
		itemsReversed() {
			return [...this.items].reverse()
		},
	},
	methods: {
		// Задача 1: Добавляем новый элемент в конец списка
		addItemToEnd() {
			if (this.newItem.trim()) {
				this.items.push(this.newItem)
				this.newItem = '' // Очищаем инпут
			}
		},
		// Задача 2: Добавляем новый элемент в начало списка
		addItemToStart() {
			if (this.newItem.trim()) {
				this.items.unshift(this.newItem)
				this.newItem = '' // Очищаем инпут
			}
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
