<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<table border="1">
			<thead>
				<tr>
					<th>ID</th>
					<th>Имя</th>
					<th>Зарплата</th>
					<th>Возраст</th>
					<th>Удалить</th>
					<th>Редактировать</th>
				</tr>
			</thead>
			<tbody>
				<Employee
					v-for="(user, index) in users"
					:key="user.id"
					:user="user"
					:index="index"
					@remove="removeUser"
					@edit="editUser"
				/>
			</tbody>
		</table>

		<!-- Модальное окно для редактирования -->
		<div v-if="isEditing" class="modal">
			<div class="modal-content">
				<h2>Редактировать пользователя</h2>
				<label for="name">Имя:</label>
				<input type="text" v-model="editedUser.name" />

				<label for="salary">Зарплата:</label>
				<input type="number" v-model="editedUser.salary" />

				<label for="age">Возраст:</label>
				<input type="number" v-model="editedUser.age" />

				<button @click="saveUser">Сохранить</button>
				<button @click="cancelEdit">Отменить</button>
			</div>
		</div>
	</div>
</template>

<script>
import Employee from './Employee.vue'

export default {
	components: {
		Employee,
	},
	data() {
		return {
			users: [
				{ id: 1, name: 'name1', salary: 100, age: 30 },
				{ id: 2, name: 'name2', salary: 200, age: 40 },
				{ id: 3, name: 'name3', salary: 300, age: 50 },
			],
			isEditing: false,
			editedUser: {},
			editingIndex: null,
		}
	},
	methods: {
		removeUser(index) {
			this.users.splice(index, 1)
		},
		editUser(index) {
			this.editedUser = { ...this.users[index] }
			this.editingIndex = index
			this.isEditing = true
		},
		saveUser() {
			this.users[this.editingIndex] = { ...this.editedUser }
			this.isEditing = false
		},
		cancelEdit() {
			this.isEditing = false
		},
	},
}
</script>

<style scoped>
.modal {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background: rgba(0, 0, 0, 0.5);
	display: flex;
	justify-content: center;
	align-items: center;
}

.modal-content {
	background: white;
	padding: 20px;
	border-radius: 5px;
	width: 300px;
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
