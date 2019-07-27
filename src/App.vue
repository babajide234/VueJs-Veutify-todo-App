<template>
  <v-app>
   
    
    <v-content>
      <v-container fluid fill-height>
        <v-layout align-center justify-center>
          
          <v-flex xs12 sm8 md4>
            <v-card class="elevation-12">
               <v-toolbar dark color="primary">
                 <v-toolbar-title>
                   Todo
                 </v-toolbar-title>
               </v-toolbar>
               <v-spacer></v-spacer>
               <v-card-text>
                  <Header/>
                  <AddTodo v-on:add-todo="addTodo"/>
                  <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
               </v-card-text>
              
            </v-card>
          </v-flex>
          </v-layout>
      
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Todos from './components/Todos';
import Header from './components/layout/Header';
import AddTodo from './components/AddTodo';


export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data () {
    return {
      //
       todos:[
       {
         id:1,
         title:"Todo One",
         completed:false
       },
       {
         id:2,
         title:"Todo Two",
         completed:true
       },
       {
         id:3,
         title:"Todo Three",
         completed:false
       }
     ]
    }
    },
   methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      this.todos=[...this.todos, newTodo]
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

</style>
