<template>
    <div>
        <h1>
            事件
        </h1>
        <p>{{ count }}</p>
        <button @click="count++">   点击增加 </button>
    </div>

    <div>
        <h1>
            事件
        </h1>
        <p>{{ count2 }}</p>
        <button @click="addCount">   点击 </button>

        <p>{{ msg}}</p>
        <button @click="show('hello',$event)"> 点击一下</button>
    </div>
    
    <a href="https://www.baidu.com/" @click="clikHandle">百度连接</a>

<div>
    <p @click="addList">{{ msg }}</p>
</div>

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
export  default{
    data() {
        return{ count:0,
                count2:0,
                msg:'新建列表',
                newItem: '',
                list:['7：00 跑步','8：00 吃早饭','9：00 吃午饭']
               
            }
        
    },
    methods:{
        addCount(e){
            //this可以访问data中的数据。
            console.log(e,"这是第"+this.count2+"次点击")
            this.count2++
        },
        show(item,$event){

            console.log(item)
            this.msg=this.msg+this.count2+item
        },
        vieewName(item){
            this.msg=item,
            console.log(item)
        },
        clikHandle(e){
            e.prenventDefault(),
            console.log('点击了')
        },
        disPlay(index){

            this.list.splice(index,1)
        },
        addItem() {
      if (this.newItem.trim()) {
        this.list.push(this.newItem.trim());
        this.newItem = '';
      }
    }

       
    }
}
</script>