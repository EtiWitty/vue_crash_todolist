<template>
	<div>
		<p>Todo Item</p>
	</div>
</template>

<script>
export default {
	name:"TodoItem"
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
	padiing: 5px 9px;
	border-radius: 50%;
	cursor: pointer;
	float: right;
}

</style>