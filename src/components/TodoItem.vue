<template>
    <v-layout row wrap>
        <v-flex xs12>       
            <v-list >
                <v-list-tile>
                    <v-list-tile-action>
                        <v-checkbox 
                            type="checkbox" 
                            v-on:change="markComplete"
                        ></v-checkbox>
                    </v-list-tile-action>
                    <v-list-tile-content>
                        <v-list-tile-title class="title text-uppercase" v-text="todo.title" v-bind:class="{'is-complete':todo.completed}"></v-list-tile-title>
                    </v-list-tile-content>
                    <v-list-tile-avatar>
                        <v-btn  fab small left dark color="red" @click="$emit('del-todo', todo.id)" ><v-icon dark>delete</v-icon></v-btn>
                    </v-list-tile-avatar>
                </v-list-tile>

            </v-list>
        </v-flex> 
            <!-- <v-flex xs4>
                <v-checkbox 
                type="checkbox" 
                v-on:change="markComplete"
                ></v-checkbox>
                 
            </v-flex>
            <v-flex xs4 >
                {{todo.title}}
            </v-flex>
            <v-flex xs4>
                <v-btn  fab small left dark color="red" @click="$emit('del-todo', todo.id)" ><v-icon dark>remove</v-icon></v-btn>
            </v-flex> -->
            
        
    </v-layout>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed= !this.todo.completed;
        }
    }
}
</script>

<style scoped>
.is-complete{
    text-decoration: line-through;
}
</style>
