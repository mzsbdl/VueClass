<template>
<form >
    <input v-model="newItem" @keyup.enter="addItem" placeholder="添加 TODO">
    <!-- <input type="button" value="提交" > -->

    <div v-for="(item,index) in list" :key="index">
        <span>{{ item }}</span>
        <button @click="disPlay(index)">完成</button>
        <hr/>
    </div>
</form>
</template>


<script>

export default {
    data() {
      return {
        msg:'新建列表',
                newItem: '',
                list:['7：00 跑步','8：00 吃早饭','9：00 吃午饭']
      };
    },
    methods: {
        disPlay(index){

            this.list.splice(index,1)
            },
      addItem() {
        if (this.newItem.trim()) {
          this.items.push(this.newItem.trim());
          this.newItem = '';
        }
      }
    }
}
</script>