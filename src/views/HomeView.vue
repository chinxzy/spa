<template>
  <div class="container">
    <addTodo />
    <TodosView />
  </div>
</template>

<script>
// @ is an alias to /src
import TodosView from '@/components/TodosView.vue'
import addTodo from '@/components/addTodo.vue'

export default {
  name: 'HomeView',
  components: {
    TodosView,
    addTodo
  }
}
</script>
