<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Чекбоксы для выбора языков -->
		<div>
			<label>
				<input type="checkbox" value="JavaScript" v-model="languages" />
				JavaScript
			</label>
			<label>
				<input type="checkbox" value="Python" v-model="languages" /> Python
			</label>
			<label>
				<input type="checkbox" value="Java" v-model="languages" /> Java
			</label>
			<label>
				<input type="checkbox" value="C++" v-model="languages" /> C++
			</label>
			<label>
				<input type="checkbox" value="Ruby" v-model="languages" /> Ruby
			</label>
		</div>

		<!-- Вывод выбранных языков в виде списка -->
		<ul>
			<li v-for="(language, index) in languages" :key="index">
				{{ language }}
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	data() {
		return {
			languages: [], // Массив для выбранных языков
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
