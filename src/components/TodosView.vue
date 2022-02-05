<template>
    
        <h3>Todos</h3>
        <div class="row todos">
        <div class="container-fluid todo" v-for="todo in allTodos" :key="todo">
            <img :src="message" alt="" class="img-fluid">
            
            <i class="fas fa-trash-alt" @click="deleteTodo(todo.id)"></i>
        </div>
      
    </div>
   
</template>

<script>
import { mapGetters, mapActions } from 'vuex'

export default {
    name: "TodosView",
    computed: {
        ...mapGetters(['allTodos']),
    },
    methods: {
        ...mapActions(['fetchTodos', 'deleteTodo']),
    },
    created() {
        this.fetchTodos()
    }
}
</script>
<style scoped>
.todos{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem
} 
.todo{
    border: 1px solid #ccc;
    background: #41b883;
    padding: 1rem;
    border-radius: 5px;
    position: relative;
    text-align: center;
    cursor: pointer;
}
i{
    position: absolute;
    bottom: 10px;
    right: 10px;
    color: #fff;
    cursor: pointer;
}
</style>