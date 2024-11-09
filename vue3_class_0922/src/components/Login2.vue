<template>

<div  class="loginview">
  <div class="container">
  <div class="header-box"> 
  </div>
  
  <div class="login-box">
      <h2>用户登录</h2>
      <form>
      <label for="username">用户名：</label>
      <input type="text" required: v-model="username" id="username" >
      <p v-if="usernameError" class="error">{{ usernameError }}</p>
      <br>
      <label for="password">密码：  </label>
      <input type="password" v-model="password" id="password">
      <p v-if="passwordError" class="error">{{ passwordError }}</p>
      <br>
      <button @click.prevent="login">登录</button>
      <button @click.prevent="register">注册</button>
    </form>
    </div>
  </div>
</div>
</template>
<script>
export default {
  data() {
    return {
      username: '',
        password: '',
        usernameError: '',
        passwordError: ''
    };
  },
  mounted() {
    
  },
  methods: {
    login() {
     
      this.passwordError = '';
          if (!this.username) {
            this.usernameError = '用户名不能为空';
            return;
          }else{
            this.usernameError = '';
          }
          if (!this.password) {
            this.passwordError = '密码不能为空';
            return;
          }else{
            this.passwordError = '';
          }
          
          
          console.log('尝试登录，用户名：', this.username, '密码：', this.password);
        },
        register() {
          this.usernameError = '';
          this.passwordError = '';
          if (!this.username) {
            this.usernameError = '注册用户名不能为空';
            return;
          }
          if (!this.password) {
            this.passwordError = '注册密码不能为空';
            return;
          }
          // 这里可以添加实际的注册逻辑，比如发送请求到后端进行注册
          console.log('尝试注册，用户名：', this.username, '密码：', this.password);
        }
  }
};
</script>
<style>
.error{
  color: red;
  font-size: 12px;
  margin-top: 5px;
}
input {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 3px;
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
   color:black;
   font-size:15px;
   padding: 20px 40px;
}
button{
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
</style>