<template>
<div>
    <!--JavaScript expressions in Vue are enclosed in double curly brackets.-->
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <!-- we are now passing the data to the todo component to render the todo list-->

    <todo v-for='(todo , index) in todos'  v-bind:item="item"  v-bind:index="index"></todo>

    <!-- we use the v-on to attach event listeners thus we have attached an event listener that will call the method delete todo-->
    <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></todo>
    </div>

    </template>



<script type ="text/javascript">
import Todo from './Todo';

export default{
props:['todos'],
components: {
Todo,
},

methods:{

  deleteTodo(todo){

  const todoIndex = this.todos.indexOf(todo);
  this.todos.splice(todoIndex, 1);

},

},
};
</script>
<style>
</style>
