<template>
  <div class="wrapper">
    <img class="wrapper__img" src="../../assets/编组@2x.png"/>
    <div class="wrapper__input">
      <input v-model="data.username" class="wrapper__input__content" placeholder="请输入账号"/>
    </div>
    <div class="wrapper__input">
      <input v-model="data.password" class="wrapper__input__content" placeholder="请输入密码" type="password"/>
    </div>
    <div class="wrapper__login-button" @click="handleLogin">登录</div>
    <div class="wrapper__login-link" @click="handleRegisterClick">立即注册</div>
  </div>
</template>

<script>
import { useRouter } from 'vue-router'
import { reactive } from 'vue'
import axios from 'axios'

export default {
  name: 'Login',
  setup () {
    const data = reactive({
      username: '',
      password: ''
    })
    const router = useRouter()
    const handleLogin = () => {
      axios.post('https://www.fastmock.site/mock/5f86c4dc97675d047070bcafa9385d27/api/api/user/login', {
        username: data.username,
        password: data.password
      }).then(() => {
        alert('登录成功')
        localStorage.isLogin = true
        router.push({ name: 'Home' })
      }).catch(() => {
        alert('登录失败')
      })
    }
    const handleRegisterClick = () => {
      router.push({ name: 'Register' })
    }
    return { handleRegisterClick, handleLogin, data }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';
.wrapper {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  transform: translateY(-50%);

  &__img {
    display: block;
    margin: 0 auto .4rem auto;
    width: .66rem;
    height: .66rem;
  }
  &__input {
    height: .48rem;
    margin: 0 .4rem .16rem .4rem;
    padding: 0 .16rem;
    background: #F9F9F9;
    border: 1px solid rgba(0, 0, 0, 0.10);
    border-radius: 6px;

    &__content {
      line-height: .48rem;
      border: none;
      outline: none;
      width: 100%;
      background: none;
      font-size: .16rem;
      color: $content-notice-fontcolor;

      &::placeholder {
        color: $content-notice-fontcolor;
      }
    }
  }
  &__login-button {
    margin: .32rem .4rem .16rem .4rem;
    line-height: .48rem;
    background: #0091FF;
    box-shadow: 0 .04rem .08rem 0 rgba(0, 145, 255, 0.32);
    border-radius: .04rem;
    color: #fff;
    font-size: .16rem;
    text-align: center;
  }

  &__login-link {
    text-align: center;
    font-size: .14rem;
    color: $content-notice-fontcolor;
  }
}
</style>
