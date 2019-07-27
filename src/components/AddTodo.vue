<template>
    <div>
        <v-form @submit="addTodo">
            <v-text-field prepend-icon="person" type="text" name="title"  v-model="title" placeholder="ADD TODO...."></v-text-field>
            <v-btn fab dark small color="Primary" type="submit" ><v-icon>add</v-icon></v-btn>
        </v-form>
    </div>
</template>

<script>
import uuid from "uuid";

export default {
    name: "AddTodo",
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);
            this.title='';
        }
    }
}
</script>

<style scoped>

</style>
