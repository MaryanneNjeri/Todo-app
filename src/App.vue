<template>
  <div>

  <todo-list v-bind:todos="todos"></todo-list>
  </div>
</template>

<script>

import TodoList from './components/TodoList'
export default {
name:'app',
components:{
TodoList,
},
data(){
return{
todos:[{
title:'Todo A',
project:'Project A',
Author:'Lisa Woods',
done: false,
},
{
title:'Todo B',
project:'project B',
Author:'Mary',
done:true,
}
,{
title :'Todo C',
project:'Project C',
Author:'Leo',
done:false,
},
{
title:'Todo D',
project:'project D',
Author:'Suzan',
done:false
}],

};
},
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
