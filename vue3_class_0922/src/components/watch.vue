<template>
    <div>
        <h1>
            事件
        </h1>
        <p>{{ count }}</p>
        <button @click="count++">   点击增加 </button>
    </div>
</template>
<script>
export default {
    data(){
        return {
            count: 0,
            obj：{}
        };
    },
    watch:{
        count(newValue, oldValue){
            console.log(newValue, oldValue)
        },
        
	obj:{
        handler(newValue,oldValue){
		console.log(newValue,oldValue)
	}
    deep:true
}
    }

    
}

</script>