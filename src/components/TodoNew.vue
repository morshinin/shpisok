<template>
	<form @submit.prevent="addTodo" class="mb-10">
		<input
			class="border px-4 py-2 w-72 outline-none"
			type="text"
			placeholder="Введи текст здесь..."
			v-model="task"
		/>
		<button type="submit" class="px-4 py-2 bg-blue-400 hover:bg-blue-500 text-white border-blue-400 border">+</button>
	</form>
</template>

<script>
	export default {
		data() {
			return {
				task: '',
				newId: 0
			}
		},

		methods: {
			addTodo: function() {
				if (this.task === '') {
					return;
				}
				this.$store.dispatch('addTodo', this);
				this.newId++;
				this.task = '';
			}
		}
	}
</script>