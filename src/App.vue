<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<ul>
			<li
				v-for="(item, index) in items"
				:key="index"
				@click="removeItem(index)"
			>
				{{ item }}
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	data() {
		return {
			items: ['Элемент 1', 'Элемент 2', 'Элемент 3', 'Элемент 4'],
		}
	},
	methods: {
		// Метод для удаления элемента из массива
		removeItem(index) {
			this.items.splice(index, 1) // Удаляем элемент по индексу
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
