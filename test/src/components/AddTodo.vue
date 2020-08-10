<template>
	<div>
		<!-- like "delete", we have to move upward to app.vue to access to the array of data in it -->
		<form @submit="addTodo">
			<input type="text" v-model="title" name="title"  placeholder="Add Todo...">
			<input type="submit" value="Submit" class="btn">
		</form>
	</div>
</template>

<script>
import uuid from 'uuid';

export default {
	name: "AddTodo",
	data() {
		return {
			title: ''
		}
	},
	methods: {
		addTodo() {
			// construct our todo item object
			const newTodo = {
				id: uuid.v4(),
				title: this.title,
				completed: false
			}
			// sent up to parents by emitting
			this.$emit('add-todo', newTodo);
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