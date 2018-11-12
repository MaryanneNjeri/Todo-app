<template>

<div class="ui centered card">

<div class ='content'>
<div class='header'>
{{ todo.Author}}
</div>
<div class='meta'>
{{id}} {{ todo.project }}
</div>
<div class ='extra content'>
  <span class='right floated edit icon ' v-on:click='showForm'>
  <i class='edit icon'></i>
  </span>

  <span class='right floated trash icon' v-on:click="deleteTodo(todo)">
  <i class="trash icon"></i>
  </span>

  </div>
  </div>
  <div class="content" v-show='isEditing'>
  <div class='ui form'>
  <div class='field'>
  <label>Title</label>
  <input type='text' v-model='todo.title'>
  </div>
  <div class='field'>
  <label>Project</label>
  <input type='text' v-model='todo.title'>
  </div>
  <div class ='ui two button attached buttons'>
  <button class='ui basics blue button' v-on:click='hideForm'>
  Close X
  </button>
  </div>
  </div>
  </div>
  <div class ='ui bottom attachted green basic button' v-show='todo.done'>
  Completed
  </div>
  <div class ='ui bottom attached red basic button' v-show='!todo.done'>
  Complete
  </div>
  </div>
  </template>
  <script type="text/javascript">
  export default {
  props: ['todo'],
  data(){
  return {
  isEditing:false,
  };

  },
  methods:{

  showForm(){
  this.isEditing=true;
  },

  deleteTodo(todo){
  alert("Are you sure you want to delete");
  this.$emit('delete-todo',todo);
  },

  hideForm(){
  this.isEditing=false;
  },
  
  },
  };
  </script>
