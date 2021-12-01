<template>
  <div id="app" class="container mx-auto">
    <h1 class="mb-10 text-gray-600 text-2xl font-bold uppercase">
      Шписок
    </h1>
    <TodoNew />
    <TodoList />
  </div>
</template>

<script>
import TodoNew from '@/components/TodoNew.vue'
import TodoList from '@/components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    TodoNew
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
