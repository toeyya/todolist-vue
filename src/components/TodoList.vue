<template>
    <div>
        <!-- <div class="ui centered card" v-for="todo in todos">
            <div class="content">
                <div class="header">{{todo.title}}</div>
                <div class="meta">{{todo.project}}</div>
                <div class="extra content">
                    <span class='right floated edit icon'>
                        <i class='edit icon'></i>
                    </span>
                </div>
            </div>
            <div class ='ui bottom attached green basic button' v-show="todo.done">Completed</div>
            <div class ='ui bottom attached red basic button' v-show="!todo.done">Complete</div>
        </div>       -->
        <todo v-on:delete-todo = "deleteTodo" v-for = "todo in todos" :todo = "todo" :key = "todo.project"
              v-on:get-data = "getData" ></todo>
    </div>
</template>
<script type="text/javascript">
import Todo from './Todo'
/* eslint-disable */ 
export default {
    props: ['todos'] ,
    data(){
        return {
            msg: ''
        }
    },
    components: {
        Todo,
    },
    methods: {
        deleteTodo(todo) {
            const todoIndex =  this.todos.indexOf(todo);
            this.todos.splice(todoIndex,1);
        },
        getData(todo){
            this.msg = todo.title + ' test naja';
            alert(this.msg);
        }
    },
}
</script>
<style></style>