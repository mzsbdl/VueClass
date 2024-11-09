<template>

<div class="finish">
    <!-- 完成列表 -->

    <div class="todo-list">
        <div class="todo-item" v-for="item in todofinish" :key="item">
            <div class="todo-text">{{item}}</div>
            
        </div>
    </div>
</div>
</template>
<script>
export default {

    name: 'finish',
    props:{
        todofinish:Array
    },
    
    
    
    data(){
        return {

            
        }
    },
    mounted(){

    }
}
</script>