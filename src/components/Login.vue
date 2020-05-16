/* eslint-disable */
<template>
<div class="login_container">
    <div class="login_box">
        <!-- 头像区域 -->
        <div class="avatar_box">
            <img src="../assets/logo.png" alt="">
        </div>
        <!-- 表单区域 -->
        <el-form :rules="loginFormRules" :model="loginForm" class="login_form" label-width="0px">
            <!-- 用户名 -->
  <el-form-item prop="username">
    <el-input v-model="loginForm.username" prefix-icon="el-icon-user" placeholder="username" clearable></el-input>
  </el-form-item>
  <!-- 密码 -->
  <el-form-item prop="password">
    <el-input type="password" v-model="loginForm.password" prefix-icon="el-icon-lock" placeholder="password" clearable></el-input>
  </el-form-item>
  <!-- 按钮 -->
   <el-form-item class="btns">
    <el-button type="primary">登录</el-button>
     <el-button type="info">重置</el-button>
  </el-form-item>
        </el-form>
    </div>
</div>
</template>
<script>
export default {
  data () {
    return {
      loginForm: {
        username: 'madoka',
        password: '123456'
      },
      loginFormRules: {
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur' },
          { min: 3, max: 10, message: '长度在3到10个字符', trigger: 'blur' }
        ],
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' },
          { min: 6, max: 15, message: '长度在6到15个字符', trigger: 'blur' }
        ]
      }
    }
  }
}
</script>
<style lang="less" scoped>
.login_container{
    background-color:#2b4b6b;
    height:100%;
}
.login_box{
    width:450px;
    height:300px;
    background-color: rgb(255, 233, 237);
    border-radius: 3px;
    position: absolute;
    left:50%;
    top:50%;
    transform:translate(-50%,-50%);

    .avatar_box{
        height:130px;
        width:130px;
        border:1px solid #eee;
        border-radius: 50%;
        padding: 10px;
        box-shadow: 0 0 10px #ddd;
        position: absolute;
        left:50%;
        transform: translate(-50%,-50%);
        background-color: rgb(247, 185, 255);
        img{
            width:100%;
            height:100%;
            border-radius: 50%;
            background-color: #fff;
        }
    }
}
.login_form{
    position:absolute;
    bottom:0;
    width:100%;
    padding: 0 20px;
    box-sizing:border-box;
}
.btns{
    display: flex;
    justify-content: flex-end;
}
</style>
