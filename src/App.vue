<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div class="container">
		<!-- Вывод списка -->
		<ul class="item-list">
			<li v-for="(item, index) in items" :key="index" class="item">
				{{ item }}
			</li>
		</ul>

		<!-- Кнопки для различных операций -->
		<div class="buttons">
			<button @click="addItem" class="button">Добавить элемент в конец</button>
			<button @click="removeFirstItem" class="button">
				Удалить первый элемент
			</button>
			<button @click="removeLastItem" class="button">
				Удалить последний элемент
			</button>
			<button @click="removePenultimateItem" class="button">
				Удалить предпоследний элемент
			</button>
			<button @click="sortItems" class="button">Отсортировать</button>
			<button @click="reverseItems" class="button">Развернуть список</button>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			items: ['item1', 'item2', 'item3'],
		}
	},
	methods: {
		addItem() {
			this.items.push('newItem')
		},
		removeFirstItem() {
			this.items.shift()
		},
		removeLastItem() {
			this.items.pop()
		},
		removePenultimateItem() {
			if (this.items.length > 1) {
				this.items.splice(this.items.length - 2, 1)
			}
		},
		sortItems() {
			this.items.sort()
		},
		reverseItems() {
			this.items.reverse()
		},
	},
}
</script>

<style scoped>
/* Основные стили контейнера */
.container {
	font-family: Arial, sans-serif;
	padding: 20px;
}

/* Стили для списка */
.item-list {
	list-style-type: none;
	padding: 0;
	margin-bottom: 20px;
}

.item {
	font-size: 18px;
	background-color: #f4f4f4;
	margin: 5px 0;
	padding: 10px;
	border-radius: 5px;
	transition: background-color 0.3s ease;
}

.item:hover {
	background-color: #e0e0e0;
}

/* Стили для кнопок */
.buttons {
	display: flex;
	flex-direction: column;
	gap: 10px;
}

.button {
	padding: 10px 15px;
	background-color: #007bff;
	color: white;
	border: none;
	border-radius: 5px;
	cursor: pointer;
	font-size: 16px;
	transition: background-color 0.3s ease;
}

.button:hover {
	background-color: #0056b3;
}

.button:active {
	background-color: #004085;
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
