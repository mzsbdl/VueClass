<template>

  <div  class="loginview">
   
    <div class="header-box">
       xx管理类系统
    </div>
    <div class="container-box">
    
        <div class="login-box-title">用户登录</div>
        <div v-for="(item,index) in fields"class="login-box-form">
          <div class="field">{{item.title}}<span v-if="item.required" style="color: red;">*</span></div>
           <input v-model="item.model" class="input" :type="item.type"/>
           <div class="tip" v-if="index==1" >请确认密码长度需要大于6位</div>
     
        </div>
        <div class="resiginer-btn">注册账号</div>
        <button @click="createAccount" class="btn">登录</button>
      </div>
    
  </div>
  </template>
  <script>
  export default {
    data() {
      return {
        title:"数学与计算机学院-后台管理系统",
        fields:[{
          title:'用户名',type:'text',model:'',required:true
        },
        {
          title:'密码',type:'password',model:'',required:true
        }
        
          

        ]
      };
    },
    mounted() {
      
    },
    computed:{
      password:{
        get(){
          return this.fields[2].model;
        }},
        set(value){
          this.fields[2].model=value;
        }
      }
    ,
    methods: {
      craeteAccount(){
        if(this.name.length==0){
          alert("请输入用户名")
          return
        }else if(this.password.length<=6){
          alert("请输入密码")
          return
        }
        alert("注册成功")
      }
          }}
  </script>
  <style>
  .red{
    color: red;
  }
  .error{
    color: red;
    font-size: 12px;
    margin-top: 5px;
  }
  .login-box-form{
    font-size: 24px;
    margin-top: 18px;
  }
  .input {
    width: 98%;
    height: 30px;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  .field{

  }
  .top{

  }
  label {
    display: block;
    margin-bottom: 5px;
  }
  h2 {
    text-align: center;
    margin-bottom: 20px;
  }
  .loginview{
      width: 100%;
      height: 100vh;
      background-image: url("../assets/login.jpg");
      background-size: cover;
      background-repeat: no-repeat;
      
  }
  .header-box{
     color:#fff;
     font-size:30px;
     padding: 20px 40px;
     font-weight: bold;
  }
  .resiginer-btn{
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    margin-top: 15px;
  }
  .btn{
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    margin-top: 15px;
  }
  .login-box{
    width: 400px;
    height: 400px;
    position: absolute;
    top: 200px;
    right: 9%;
    background: #fff;
    padding :20px;
    border-radius: 10px ;
  }
  .container{
    position: relative;
  }
  .login-box-title{
    font-size:24px;
    text-align: center;
  }
  
  </style>