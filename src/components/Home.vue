<template>
<div>
   <img src="../assets/logo.png" alt="">
   <h1>Todo-App</h1>
<hr>
    <input @keyup.enter="add" type="text" placeholder="Write something....." v-model="word">
    <button @click="add">Add to list</button>
    
    <ul>
      <li v-for="(todo, index) in todos" :key="todo">{{ todo }} 
        <span class="remove" @click="remove(index)">x</span>
      </li>
      
    </ul>
</div>
   
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      word: '',
      todos: [],
      
      
    }
  },
  methods: {
    add(){
        if(this.word != ''){
           this.todos.unshift(this.word);
            this.word = '';
        }
        
            
        
    },
    remove(id){
       //this.todos.splice(id, 1) this is using JS
       //now using vue.js
       this.$delete(this.todos, id)
    }
  }
  
   
  
}
</script>


