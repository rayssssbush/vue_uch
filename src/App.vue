<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Задача 1: Квадратный корень числа -->
		<input
			v-model.number="numberForSqrt"
			type="number"
			placeholder="Введите число"
		/>
		<button @click="calculateSqrt">Посчитать квадратный корень</button>
		<p>{{ sqrtResult }}</p>

		<!-- Задача 2: Сумма двух чисел -->
		<input
			v-model.number="firstNumber"
			type="number"
			placeholder="Введите первое число"
		/>
		<input
			v-model.number="secondNumber"
			type="number"
			placeholder="Введите второе число"
		/>
		<button @click="calculateSum">Посчитать сумму</button>
		<p>{{ sumResult }}</p>

		<!-- Задача 3: Обмен текста между инпутами -->
		<input v-model="text1" placeholder="Введите текст в первый инпут" />
		<input v-model="text2" placeholder="Введите текст во второй инпут" />
		<button @click="swapText">Поменять текст</button>
		<p>Текст в первом инпуте: {{ text1 }}</p>
		<p>Текст во втором инпуте: {{ text2 }}</p>

		<!-- Задача 4: Разделение ФИО на фамилию, имя и отчество -->
		<input v-model="fullName" placeholder="Введите ФИО" />
		<button @click="splitFullName">Разделить ФИО</button>
		<p>Фамилия: {{ surname }}</p>
		<p>Имя: {{ name }}</p>
		<p>Отчество: {{ patronymic }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			numberForSqrt: 0,
			sqrtResult: null,
			firstNumber: 0,
			secondNumber: 0,
			sumResult: null,
			text1: '',
			text2: '',
			fullName: '',
			surname: '',
			name: '',
			patronymic: '',
		}
	},
	methods: {
		calculateSqrt() {
			this.sqrtResult = Math.sqrt(this.numberForSqrt)
		},
		calculateSum() {
			this.sumResult = this.firstNumber + this.secondNumber
		},
		swapText() {
			const temp = this.text1
			this.text1 = this.text2
			this.text2 = temp
		},
		splitFullName() {
			const names = this.fullName.split(' ')
			if (names.length === 3) {
				this.surname = names[0]
				this.name = names[1]
				this.patronymic = names[2]
			} else {
				this.surname = ''
				this.name = ''
				this.patronymic = ''
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
