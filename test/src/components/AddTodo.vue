<template>
	<div>
		<!-- like "delete", we have to move upward to app.vue to access to the array of data in it -->
		<form @submit="addTodo">
			<input type="text" v-model="title" name="title"  placeholder="Add Todo...">
			<input type="submit" value="submit" class="btn">
		</form>
	</div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
	name: "AddTodo",
	data() {
		return {
			title: ''
		}
	},
	methods: {
		addTodo(e) {
			e.preventDefault();
			// construct our todo item object
			const newTodo = {
				id: uuidv4(),
				title: this.title,
				completed: false
			}
			// send up to parents by emitting
			this.$emit('add-todo', newTodo);
			this.title = '';
		}
	}
}
</script>

<style scoped>
	form {
		display: 10;
		padding: 5px;
	}

	input[type="text"] {
		flex: 10;
		padding: 5px;
	}

	input[type="submit"] {
		flex: 2;
	}
</style>