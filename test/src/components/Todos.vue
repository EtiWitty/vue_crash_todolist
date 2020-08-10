<template>
	<div>
		<div v-for="todo in todos" v-bind:key="todo.id">
			<TodoItem />
		</div>
	</div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
	name :"Todos",
	components: {
		TodoItem
	},
	props: ["todos"]
}
</script>

<style scoped>

</style>
