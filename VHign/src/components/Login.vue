<template>
  <div class="login">
    <h1>{{ msg }}</h1>
    <div class="outer_label">
      <img class="inner_label login_logo" src="../assets/logo/HignMade.png">

      <div class="login-from">
        <input type="text" class="login-form-account login-form-logo" placeholder="用户名" v-model="account">
        <input type="text" class="login-form-password login-form-logo" placeholder="密码" v-model="password">
        <el-bbutton class="login-btn" @click.native="login" type="primary" round:loading="isBtnLoading">登录</el-bbutton>
        <div style="margin-top: 10px">
          <span style="color: #000099;" @click="login">游客登陆</span>
          <span style="float: right;color: #A9A9AB">忘记密码？</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Login',
    data() {
      return {
        account: '',
        password: '',
        isBtnLoading: false,
        msg: '欢迎登录和美工作台'
      }
    },
    created() {
    },
    computed: {
      btnText() {
        if (this.isBtnLoading) {
          return "登录中...";
        }
        return "登录";
      }
    },
    methods: {
      login() {
        if (!this.account) {
          this.$message.error("请输入用户名");
          return;
        }
        if (!this.password) {
          this.$message.error("请输入密码");
          return;
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
  .login-from {
    padding: 10%;
    padding-left: 10%;
    padding-right: 10%;
  }

  .login {
    background: url("../assets/logo/login-background.jpg");
    background-size: 100% 100%;
    height: 100%;
  }

  .login-form-account {
    background: url("../assets/logo/account.png") no-repeat 3%;
    background-size: 13px 15px;
  }

  .login-form-password {
    background: url("../assets/logo/password.png") no-repeat 3%;
    background-size: 13px 15px;
    margin-bottom: 20px;
  }

  .login_logo {
    height: 100%;
  }

  .login-btn {
    width: 100%;
    font-size: 16px;
    background: linear-gradient(to right, #000099, #2154FA);
    filter: brightness(1.4);
  }
</style>
