<script>
export default {
  name: 'Login',
  data() {
    return {
      // 用于存储用户输入的用户名
      username: '',
      // 用于存储用户输入的密码
      password: '',
    }
  },
  methods: {
    // 登录
    login() {
      this.$router.push('/root')
      // 通过axios发送post请求
      // this.$axios.post('/api/login', {
      //   username: this.username,
      //   password: this.password,
      // }).then((res) => {
      //   // 登录成功
      //   if (res.data.code === 0) {
      //     // 将token存储到localStorage中
      //     localStorage.setItem('token', res.data.data.token)
      //     // 跳转到chat页面
      //     this.$router.push('/root')
      //   }
      //   else {
      //     // 登录失败
      //     this.$message.error(res.data.msg)
      //   }
      // })
    },
  },

}
</script>

<template>
  <div class="container">
    <h1 class="logo" />
    <!--    前往chat页面 -->
    <form method="post">
      <div class="title">
        蓝鲸AI俱乐部
      </div>

      <button @click="login">
        登录
      </button>
    </form>
  </div>
</template>

<style scoped>
.container {
    position: relative;
    background-image: url(/public/login-full-bg.png);
    background-size: cover;
    width: 100%;
    height: 100vh;
    max-width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.title {
    font-size: 60px;
    font-weight: bolder;
    font-style: italic;
    position: relative;
    z-index: 2;
}

/* 定义闪烁的动画 */
@keyframes blink {
    0% {
        background-color: #ff0011;
    }
    25% {
        background-color: #FFCC00;
    }
    50% {
        background-color: #44ff00;
    }
    75% {
        background-color: #FFCC00;
    }
    100% {
        background-color: #ff0011;
    }
}

.title:after {
    content: "";
    position: absolute;
    top: 5px;
    right: -24px;
    width: 38px;
    height: 38px;
    animation: blink 12s linear infinite;
    z-index: -1;
}

form {
    text-align: right;
}

button {
    font-size: 26px;
    padding: 5px 60px;
    color: #fff;
    border-radius: 10px;
    box-shadow: 0 15px 20px 0 rgba(21, 71, 194, .25);
    animation: blink 10s linear infinite;
    /*background-color: #1547c2;*/
    background-color: #4D99FF;
}

button:hover {
    animation: none;
    background-color: #4D99FF;
}
</style>
