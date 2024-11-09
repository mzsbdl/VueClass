

    
<template>

    <div >
       
    现在的时间是：
    {{ fmtTime }}
        
    </div>
    </template>
    <script type="text/javascript" src="../js/dayjs.min.js"></script>
    <script type="text/javascript">
    

    export default {
   
        name:"nowTime",
        
        
        
        
        data(){
            return {
    
                
            }
        },
        mounted(){
    
        },
        computed:{
            fmtTime(){
                return dayjs(this.time).format('YYYY年MM月DD日 HH:mm:ss')
            }
        }
    
    }
    </script>