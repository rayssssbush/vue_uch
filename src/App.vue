<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Вывод списка -->
		<ul>
			<li v-for="(item, index) in items" :key="index">{{ item }}</li>
		</ul>

		<!-- Кнопки для различных операций -->
		<button @click="addItem">Добавить элемент в конец</button>
		<button @click="removeFirstItem">Удалить первый элемент</button>
		<button @click="removeLastItem">Удалить последний элемент</button>
		<button @click="removePenultimateItem">
			Удалить предпоследний элемент
		</button>
		<button @click="sortItems">Отсортировать</button>
		<button @click="reverseItems">Развернуть список</button>
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
