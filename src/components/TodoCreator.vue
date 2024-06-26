<script setup>
import { reactive, defineEmits } from "vue";
import TodoButton from "./TodoButton.vue";

const emit = defineEmits(["create-todo"])

const todoState = reactive({
  todo: "",
  invalid: null,
  errorMessage: "",
});

const createTodo = () => {
  todoState.invalid = null;
  if (todoState.todo !== "") {
    emit("create-todo", todoState.todo);
    todoState.todo = "";
    return;
  }

  todoState.invalid = true;
  todoState.errorMessage = "Todo value cannot be empty";
};
</script>

<template>
    <div class="input-wrap" :class="{ 'input-error' : todoState.invalid }">
        <input type="text" v-model="todoState.todo" />
        <TodoButton @click="createTodo()" />
    </div>
    <p v-show="todoState.invalid" class="error-message"> {{  todoState.errorMessage }}</p>
</template>

<style lang="scss" scoped>
.input-wrap {
  display: flex;
  transition: 250ms ease;
  border: 2px solid #4F7081;
  
  &.input-error {
    border-color: red;
  }

  &:focus-within {
    box-shadow: 0 -4px 12px -1px rgb(0 0 0 / 0.1),
      0 4px 12px -1px rgb(0 0 0 / 0.1);
  }

  input {
    width: 100%;
    padding: 8px 6px;
    border: none;

    &:focus {
      outline: none;
    }
  }
}

.error-message {
  margin-top: 6px;
  font-size: 14px;
  text-align: center;
  color: red;
}
</style>