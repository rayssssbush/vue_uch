<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<!-- №1: Список ссылок -->
	<ul>
		<li v-for="item in hrefs" :key="item.href">
			<a :href="item.href">{{ item.text }}</a>
		</li>
	</ul>

	<!-- №2: Таблица с продуктами -->
	<table>
		<tr v-for="product in products" :key="product.name">
			<td>{{ product.name }}</td>
			<td>{{ product.price }}</td>
			<td>{{ product.quantity }}</td>
		</tr>
	</table>
</template>

<script>
export default {
	data() {
		return {
			hrefs: [
				{ href: '1.html', text: 'text1' },
				{ href: '2.html', text: 'text2' },
				{ href: '3.html', text: 'text3' },
			],
			products: [
				{ name: 'product1', price: 100, quantity: 5 },
				{ name: 'product2', price: 200, quantity: 4 },
				{ name: 'product3', price: 300, quantity: 3 },
			],
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
