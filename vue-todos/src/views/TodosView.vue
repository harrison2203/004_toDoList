<script setup>
import {ref} from "vue";
import {uid} from 'uid'; // unique identifier. chaque élément aura un id unique
import TodoCreatorComponent from '../components/TodoCreatorComponent.vue';

const todoList = ref([]);

const createTodo = (todo) => {
  todoList.value.push({
    id: uid(),
    todo,
    isCompleted: null,
    isEditing: null
  })
}



</script>

<template>
  <main>
    <h1>Create Todo</h1>
    <TodoCreatorComponent @create-todo="createTodo"/>
  </main>
</template>

<style scoped lang="scss">
main {
  display: flex;
  flex-direction: column;
  max-width: 500px;
  width: 100%;
  margin: 0 auto;
  padding: 40px 16px;

  h1 {
    margin-bottom: 16px;
    text-align: center;
  }
}


</style>