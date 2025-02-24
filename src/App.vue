<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Селект для выбора дня недели -->
		<select v-model="selectedDay">
			<option v-for="day in days" :key="day" :value="day">{{ day }}</option>
		</select>
		<p>Вы выбрали: {{ selectedDay }}</p>

		<!-- Селект для выбора дня, месяца и года -->
		<div>
			<select v-model="selectedDayOfMonth">
				<option v-for="i in 31" :key="i" :value="i">{{ i }}</option>
			</select>
			<select v-model="selectedMonth">
				<option v-for="month in months" :key="month" :value="month">
					{{ month }}
				</option>
			</select>
			<select v-model="selectedYear">
				<option v-for="year in years" :key="year" :value="year">
					{{ year }}
				</option>
			</select>
		</div>

		<p>
			Вы выбрали: {{ selectedDayOfMonth }} {{ selectedMonth }}
			{{ selectedYear }}
		</p>
	</div>
</template>

<script>
export default {
	data() {
		const today = new Date()
		return {
			days: [
				'Понедельник',
				'Вторник',
				'Среда',
				'Четверг',
				'Пятница',
				'Суббота',
				'Воскресенье',
			],
			months: [
				'Январь',
				'Февраль',
				'Март',
				'Апрель',
				'Май',
				'Июнь',
				'Июль',
				'Август',
				'Сентябрь',
				'Октябрь',
				'Ноябрь',
				'Декабрь',
			],
			years: Array.from(
				{ length: 101 },
				(_, i) => today.getFullYear() - 50 + i
			), // Пример диапазона годов
			selectedDay: this.days[today.getDay()], // Текущий день недели
			selectedDayOfMonth: today.getDate(), // Текущий день месяца
			selectedMonth: this.months[today.getMonth()], // Текущий месяц
			selectedYear: today.getFullYear(), // Текущий год
		}
	},
}
</script>
<template>
	<div>
		<!-- Инпут -->
		<input
			v-bind:disabled="isDisabled"
			type="text"
			placeholder="Введите текст"
		/>

		<!-- Кнопка для блокировки/отблокировки инпута -->
		<button @click="toggleInput">Toggle Input</button>

		<!-- Чекбокс для управления состоянием инпута -->
		<label>
			<input type="checkbox" v-model="isChecked" />
			Блокировка инпута
		</label>

		<p>Инпут {{ isDisabled ? 'заблокирован' : 'отблокирован' }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			isDisabled: false, // Начальное состояние инпута
			isChecked: true, // Чекбокс по умолчанию отмечен
		}
	},
	watch: {
		// Если чекбокс изменяет свое состояние, обновляем состояние инпута
		isChecked(newValue) {
			this.isDisabled = !newValue
		},
	},
	methods: {
		// Метод для переключения блокировки инпута
		toggleInput() {
			this.isDisabled = !this.isDisabled
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
