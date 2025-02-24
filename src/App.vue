<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<!-- Форма для добавления нового работника -->
		<h2>Add New Employee</h2>
		<form @submit.prevent="addEmployee">
			<label for="name">Name:</label>
			<input type="text" id="name" v-model="newEmployee.name" required />

			<label for="salary">Salary:</label>
			<input type="number" id="salary" v-model="newEmployee.salary" required />

			<label for="age">Age:</label>
			<input type="number" id="age" v-model="newEmployee.age" required />

			<button type="submit">Add Employee</button>
		</form>

		<h3>Employee List</h3>
		<ul>
			<li v-for="employee in users" :key="employee.id">
				{{ employee.name }} - {{ employee.salary }} - {{ employee.age }}
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	data() {
		return {
			newEmployee: {
				name: '',
				salary: '',
				age: '',
			},
			users: [
				{ id: 1, name: 'name1', salary: 100, age: 30 },
				{ id: 2, name: 'name2', salary: 200, age: 40 },
				{ id: 3, name: 'name3', salary: 300, age: 50 },
			],
		}
	},
	methods: {
		addEmployee() {
			// Генерация нового ID для добавленного работника
			const newId = this.users.length + 1
			// Добавление нового работника в список
			this.users.push({ ...this.newEmployee, id: newId })
			// Очистка формы после добавления
			this.newEmployee.name = ''
			this.newEmployee.salary = ''
			this.newEmployee.age = ''
		},
	},
}
</script>

<style scoped>
form {
	margin-bottom: 20px;
}

input {
	margin: 5px;
	padding: 5px;
}

button {
	padding: 5px 10px;
	margin-top: 10px;
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
