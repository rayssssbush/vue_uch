<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
	<div>
		<table border="1">
			<thead>
				<tr>
					<th>Имя</th>
					<th>Фамилия</th>
					<th>Возраст</th>
				</tr>
			</thead>
			<tbody>
				<Employee
					v-for="(user, index) in users"
					:key="user.id"
					:firstName="user.firstName"
					:lastName="user.lastName"
					:age="user.age"
				/>
			</tbody>
		</table>
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
				{ id: 1, firstName: 'John', lastName: 'Doe', age: 30 },
				{ id: 2, firstName: 'Jane', lastName: 'Smith', age: 40 },
				{ id: 3, firstName: 'Michael', lastName: 'Johnson', age: 50 },
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
