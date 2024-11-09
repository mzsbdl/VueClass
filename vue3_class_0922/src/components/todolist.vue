<template>
    <div class="todo-page">
        <div class="todo-box">
            <div class="add-title">
                <span>新建任务</span>
                <input type="text" class="add-input" placeholder="请输入待办事项" v-model="todoText">
                <button class="btn" @click="addList">添加</button>
            </div>
            <div class="change-radio">
                <input type="radio" name="tab" id="pending" v-model="tabCom" value="pending">待办事项
                <input type="radio" name="tab" id="finish" v-model="tabCom" value="finish">已完成
            </div>
               
            
            <KeepAlive> 
                <component :is="tabCom" :todos="todos" :todofinish="todofinish" @remove="remove" @complete="complete"></component>
            </KeepAlive>
        </div>
    </div>
</template>
<script>
  import { compile } from 'vue';
import  Finish from '../components/todoList/finish.vue'
  import  Pending from '../components/todoList/pending.vue'
  export default {
    components:{Finish,Pending},
    data () {
      return {
       tabCom:'pending',
       todos:[],
       todofinish:[],
       todoText:''
      }
    },
    computed: {
    
    },
    methods: {
     addList(){
        
        if(this.todoText){
            this.todos.push(this.todoText)
            this.todoText=''
        }
     },
     complete(index){
        this.todofinish.push(this.todos[index])
        console.log(index)
        this.todos.splice(index,1)
     }
     ,
     remove(index){
       this.todos.splice(index,1)
     }
  }
}
</script>
<style scoped>
.todo-page {
    height: 100vh;
    width: 100%;
    background-color: #009dcd;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 14px;
}
.todo-box {
    width: 600px;
    height: 400px;
    border-radius: 20px;
    background-color: #fff;
    padding: 20px;
}
.add-title {
    color: rgb(93, 91, 91);
    font-size: 16px;
    margin: 0 10px;
}
.add-input {
    width: 200px;
    height: 25px;
    border: 1px solid #bcbdbe;
}
.btn {
    width: 60px;
    font-size: 14px;
    margin: 0 10px;
    background-color: #fff;
    color: #009dcd;
    letter-spacing: 2px;
    border: 1px solid #009dcd;
}
.change-radio {
    padding: 10px;
    text-align: center;
    font-size: 14px;
    color: #009dcd;
}
</style>
