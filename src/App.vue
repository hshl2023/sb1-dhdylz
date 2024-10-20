<script setup lang="ts">
import { ref } from 'vue'
import Login from './components/Login.vue'
import Dashboard from './components/Dashboard.vue'

const isLoggedIn = ref(false)
const username = ref('')

const handleLogin = (user: string) => {
  isLoggedIn.value = true
  username.value = user
}

const handleLogout = () => {
  isLoggedIn.value = false
  username.value = ''
}
</script>

<template>
  <div class="app">
    <h1>教学管理系统</h1>
    <Login v-if="!isLoggedIn" @login="handleLogin" />
    <Dashboard v-else :username="username" @logout="handleLogout" />
  </div>
</template>

<style scoped>
.app {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}
</style>