<template>
  <div style="display: inline-block; margin-bottom: 60px;">
    <img class="main-img" src="http://img.paascloud.net/login/paascloud/paascloud.png" alt="">
    <div class="res">
      <div class="main-top">
        <i class="fa fa-user-o" aria-hidden="true"></i>
        <span class="login">登录</span>
        <a href="#" class="login-register" @click="loadPage('Register')">注册</a>
      </div>
      <div class="main-bot">
        <input class="login-input" @keyup.13="doLogin" v-model="loginForm.loginName" type="text" placeholder="请输入帐号"/>
        <input class="login-input" @keyup.13="doLogin" v-model="loginForm.loginPwd" type="password"
               placeholder="请输入密码"/>
        <div class="image-code-div">
          <input type="text" v-model="loginForm.captchaCode" placeholder="验证码">
          <img v-lazy="imageCode" @click="getImage"/>
        </div>
        <div class="main-password">
          <input id="button" type="checkbox" class="button" @click="rememberMeFn" :checked="rememberMe" value="Bike"
                 title=""/>
          <label for="button" class="remMe">记住我</label>
          <a class="fog" @click="loadPage('ResetPwdEmail')">忘记密码?</a>
        </div>
        <button class="login" @click="doLogin">登录</button>
        <div class="other">
          <hr/>
          <p>其他方式登录</p>
          <hr/>
        </div>
        <div class="last">
          <a href="#"><img src="../../assets/images/login/git1.png" alt=""></a>
          <a href="#"><img src="../../assets/images/login/git2.png" alt=""></a>
          <a href="#"><img src="../../assets/images/login/git3.png" alt=""></a>
          <a href="/uac/auth/qq"><img src="../../assets/images/login/git4.png" alt=""></a>
          <a href="/auth/weixin"><img src="../../assets/images/login/git5.png" alt=""></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Login",
    data() {
      return {
        imageCode: '',
        deviceId: '',
        loginForm: {
          loginName: '',
          loginPwd: '',
          captchaCode: ''
        }
      }
    }
  }
</script>

<style rel="stylesheet/scss" lang="scss">
  .image-code-div {
    width: 320px;
    height: 40px;
    margin-bottom: 14px;
    margin-bottom: 14px;

    input {
      width: 210px;
      height: 40px;
      outline: none;
      font-size: 14px;
      text-indent: 1em;
      border-radius: 2px;
      background: #F3F6F8;
      border: 1px solid #dce3e8;
    }

    img {
      width: 106px !important;
      height: 40px;
      border: 1px solid #DCE4E6;
      padding-left: 0;
      float: right;
    }

  }

  .main-img {
    width: 375px;
    margin: 27px 52.5px;
    float: left;
  }

  .main .res {
    float: right;
    width: 420px;
    margin: 0 30px;
    background-color: #ffffff;

    .main-top {
      height: 25px;
      line-height: 25px;
      margin: 10px 20px;

      i {
        font-size: 14px;
      }

      .login {
        display: inline-block;
        color: #40485b;
        font-size: 16px;
      }

      .login-register {
        float: right;
        color: #e97b21;
        font-size: 16px;
        cursor: pointer;
      }

    }

    .main-bot {
      width: 320px;
      margin: 20px 50px 30px;

      .login-input {
        width: 100%;
        height: 40px;
        margin-bottom: 20px;
        outline: 0;
        font-size: 14px;
        color: #a1a1a2;
        text-indent: 1em;
        background-color: #f3f6f8;
        border: 1px solid #dce3e8;
      }

      .button {
        width: 15px;
        height: 15px;
        vertical-align: middle;
      }

      .main-password {
        height: 20px;
        line-height: 20px;
        margin-bottom: 10px;

        .remMe {
          vertical-align: middle;
          cursor: pointer;
          color: #7e8c8d;
        }

      }

      .login {
        border: 0;
        outline: 0;
        width: 100%;
        height: 40px;
        color: #ffffff;
        cursor: pointer;
        font-size: 16px;
        margin-bottom: 20px;
        background-color: #fe7300;
      }

    }

    .other {
      width: 100%;
      height: 20px;
      line-height: 20px;
      margin-bottom: 20px;

      hr {
        width: 90px;
        display: inline-block;
        vertical-align: middle;
      }

      p {
        width: 136px;
        color: #9b9b9b;
        text-align: center;
        display: inline-block;
      }

    }

    .last {
      width: 100%;

      img {
        width: 42px;
        height: 42px;
        margin: 0 12px;
      }

      a:first-child img {
        margin-left: 0;
      }

      a:last-child img {
        margin-right: 0;
      }

    }
  }

  .fog {
    float: right;
    cursor: pointer;
  }
</style>
