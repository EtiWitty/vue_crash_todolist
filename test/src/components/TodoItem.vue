<template>
 <!-- we want to use text decoration of line-through whenever a task is completed
 so we bind a class based on the condition of todo.completed === true -->
	<div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
		<p>
			<input type="checkbox" v-on:change="markComplete">
			{{todo.title}}
			<!-- we need to go upward and traverse up to where data ia where array is
			we need to go up to todos and to app - the way to do this, is to emit an event -->
			<button @click="$emit('del-todo', todo.id)" class="del">x</button>
		</p>
	</div>
</template>

<script>
export default {
	name:"TodoItem",
	// we accept props from its parent here
	props: ["todo"],
	methods: {
		//toggle between true and false values
		markComplete() {
			this.todo.completed = !this.todo.completed
		}
	}
}
</script>

<style scoped>

.todo-item {
	background: #f4f4f4;
	padding: 10px;
	border-bottom: 1px #ccc dotted;
}

.is-complete {
	text-decoration: line-through;
}

.del {
	background: #ff0000;
	color: #fff;
	border: none;
	padding: 5px 9px;
	border-radius: 50%;
	cursor: pointer;
	float: right;
}

</style>