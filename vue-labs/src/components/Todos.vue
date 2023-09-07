<template>
    <section>
      <input type="text" name="" id="" v-model="inputTodo">
      <button @click="addTodo" class="btn">Add</button>
  
      <ul>
        <li class="list-group" v-for="todo in todoList" :key="todo.id">
          <span v-if="!todo.isEditing">{{ todo.text }}</span>
          <input v-else v-model="todo.text" @keyup.enter="updateTodo(todo)" @blur="updateTodo(todo)">
          <button class="btn" @click="toggleEdit(todo)">Edit</button>
          <button class="btn" @click="deleteTodo(todo)">Delete</button>
          <button v-if="todo.isEditing" class="btn" @click="updateTodo(todo)">Update</button>
        </li>
      </ul>
    </section>
  </template>
  
  <script>
  export default {
    name: 'Todo',
    data() {
      return {
        inputTodo: '',
        todoList: [],
      };
    },
    methods: {
      addTodo() {
        this.todoList.push({ id: Date.now(), text: this.inputTodo, isEditing: false });
        this.inputTodo = '';
      },
      deleteTodo(todoToDelete) {
        this.todoList = this.todoList.filter((todo) => todo !== todoToDelete);
      },
      toggleEdit(todo) {
        todo.isEditing = !todo.isEditing;
      },
      updateTodo(todo) {
        todo.isEditing = false;
      },
    },
  };
  </script>