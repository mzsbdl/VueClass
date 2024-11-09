<template>

<!-- 待办列表 -->
 <div class="pending">
    <div class="pending-list">
    
      
      <div v-if="show" class="pending-item" v-for="(item,index) in todos" :key="item.id">
        

        <Transition></Transition>
        <div class="pending-item-title" >{{item}}</div>
        

        <button class="btn"  @click="complete(index)" >完成</button>
        <button  class="btn" @click="remove(index)">删除</button>
    
      </div>
    
    
     
    </div>
 </div>
</template>
<script>

export default {
  name: 'pending',
  props: {

    todos:Array

  },
  data () {
    return {

       show:true
        
    }
  },
  methods: {
    complete(index){
      this.$emit('complete',index),
      this.show = !this.show
    },
    remove(index){
      this.$emit('remove',index)
    }
  }
}
</script>
<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
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
</style>