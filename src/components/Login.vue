<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits(['login'])

const username = ref('')
const password = ref('')

const handleSubmit = () => {
  if (username.value && password.value) {
    // 这里应该有真实的登录逻辑，现在只是模拟
    emit('login', username.value)
  } else {
    alert('请输入用户名和密码')
  }
}
</script>

<template>
  <div class="login">
    <h2>登录</h2>
    <form @submit.prevent="handleSubmit">
      <div>
        <label for="username">用户名：</label>
        <input id="username" v-model="username" type="text" required>
      </div>
      <div>
        <label for="password">密码：</label>
        <input id="password" v-model="password" type="password" required>
      </div>
      <button type="submit">登录</button>
    </form>
  </div>
</template>

<style scoped>
.login {
  max-width: 300px;
  margin: 0 auto;
}
form div {
  margin-bottom: 10px;
}
label {
  display: block;
  margin-bottom: 5px;
}
input {
  width: 100%;
  padding: 5px;
}
button {
  width: 100%;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}
button:hover {
  background-color: #45a049;
}
</style>