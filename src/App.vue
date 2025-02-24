<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<div v-for="(user, index) in users" :key="user.id">
			<!-- Компонент для редактирования данных работника -->
			<div>
				<p>Name: <input v-model="editableUsers[index].name" /></p>
				<p>
					Salary: <input v-model="editableUsers[index].salary" type="number" />
				</p>
				<p>Age: <input v-model="editableUsers[index].age" type="number" /></p>
				<button @click="saveChanges(index)">Save</button>
				<button @click="cancelChanges(index)">Cancel</button>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			users: [
				{ id: 1, name: 'name1', salary: 100, age: 30 },
				{ id: 2, name: 'name2', salary: 200, age: 40 },
				{ id: 3, name: 'name3', salary: 300, age: 50 },
			],
			editableUsers: [
				{ ...this.users[0] },
				{ ...this.users[1] },
				{ ...this.users[2] },
			],
		}
	},
	methods: {
		// Сохранение изменений
		saveChanges(index) {
			this.$set(this.users, index, this.editableUsers[index])
		},
		// Отмена изменений
		cancelChanges(index) {
			this.editableUsers[index] = { ...this.users[index] }
		},
	},
}
</script>

<style scoped>
input {
	margin: 5px;
}
button {
	margin: 5px;
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
