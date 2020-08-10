<template>
 <!-- we want to use text decoration of line-through whenever a task is completed
 so we bind a class based on the condition of todo.completed === true -->
	<div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
		<p>{{todo.title}}</p>
	</div>
</template>

<script>
export default {
	name:"TodoItem",
	// we accept props from its parent here
	props: ["todo"]
}
</script>

<style scoped>

.todo-item {
	background: #f4f4f4;
	padding: 10px;
	border-bottom: 1px #ccc dotted;
}

.is-complete {
	text-decoration: like-through;
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