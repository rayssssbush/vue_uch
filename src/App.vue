<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>
<template>
	<div>
		<p>Сегодня: {{ getCurrentDay() }}</p>
	</div>
</template>

<script>
export default {
	methods: {
		// Вспомогательный метод для получения дня недели по числу
		getDayByNumber(dayNumber) {
			const days = [
				'Воскресенье',
				'Понедельник',
				'Вторник',
				'Среда',
				'Четверг',
				'Пятница',
				'Суббота',
			]
			return days[dayNumber]
		},

		// Основной метод для вывода текущего дня недели
		getCurrentDay() {
			const currentDayNumber = new Date().getDay() // Получаем число дня недели (0 - Воскресенье, 1 - Понедельник и т.д.)
			return this.getDayByNumber(currentDayNumber)
		},
	},
}
</script>

<style scoped>
/* Стили по желанию */
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
