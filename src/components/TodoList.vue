<template>
	<ul class="w-72 mx-auto">
		<li
			v-for="todo in todos"
			:key="todo.id"
			class="flex items-center mb-4 cursor-pointer gap-2"
			@click="toggleTodo(todo.id)"
		>
			<span 
			class="block text-left h-full w-full px-4 py-2 shadow-md"
			:class="todo.completed ? 'line-through bg-gray-200 text-gray-500 shadow-none' : ''"
			>
				{{ todo.task }}
			</span>
			<span @click="deleteTodo(todo.id)" class="ml-auto py-2 px-4 bg-red-400 hover:bg-red-500 text-white border-red-400">-</span>
		</li>
	</ul>
</template>

<script>
	export default {
		computed: {
			todos() {
				return this.$store.getters.getTodos;
			}
		},

		methods: {
			toggleTodo: function(id) {
				this.$store.dispatch('toggleTodo', id);
			},

			deleteTodo: function(id) {
				this.$store.dispatch('deleteTodo', id);
			}
		}
	}
</script>