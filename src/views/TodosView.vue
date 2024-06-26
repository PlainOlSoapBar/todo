<script setup>
import { ref } from 'vue';
import { uid } from 'uid';
import { Icon } from '@iconify/vue';

import TodoCreator from '../components/TodoCreator.vue';
import TodoItem from '../components/TodoItem.vue';

const todoList = ref([]);

const fetchTodoList = () => {
  const savedTodoList = JSON.parse(localStorage.getItem('todoList'));
  if (savedTodoList) {
    todoList.value = savedTodoList;
  }
}

fetchTodoList();

const setTodoListLocalStorage = () => {
  localStorage.setItem('todoList', JSON.stringify(todoList.value));
};

const createTodo = (todo) => {
  todoList.value.push({
    id: uid(),
    todo,
    isCompleted: null,
    isEditing: null
  });
  setTodoListLocalStorage();
};

const toggleTodoComplete = (todoPosition) => {
  todoList.value[todoPosition].isCompleted = !todoList.value[todoPosition].isCompleted;
  setTodoListLocalStorage();
}

const toggleEditTodo = (todoPosition) => {
  todoList.value[todoPosition].isEditing = !todoList.value[todoPosition].isEditing;
  setTodoListLocalStorage();
}

const updateTodo = (newTodo, todoPosition) => {
  todoList.value[todoPosition].todo = newTodo;
  setTodoListLocalStorage();
}

const deleteTodo = (todoId) => {
  todoList.value = todoList.value.filter((todo) => todo.id !== todoId);
  setTodoListLocalStorage();
}
</script>

<template>
  <main>
    <h1>Create Todo</h1>
    <TodoCreator @create-todo="createTodo" />
    <ul class="todo-list" v-if="todoList.length > 0">
      <TodoItem
        v-for="(todo, index) in todoList"
        :todo="todo"
        :index="index"
        @toggle-complete="toggleTodoComplete"
        @edit-todo="toggleEditTodo"
        @update-todo="updateTodo"
        @delete-todo="deleteTodo"
      />
    </ul>
    <p class="todos-message" v-else>
      <Icon icon="noto-v1:sad-but-relieved-face" width="25" />
      <span>No todos yet. Create one now!</span>
    </p>
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

    .todo-list {
    display: flex;
    flex-direction: column;
    list-style: none;
    margin-top: 24px;
    gap: 20px;
  }

  .todos-message {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin-top: 24px;
  }
}
</style>