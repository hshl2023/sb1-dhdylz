<script setup lang="ts">
defineProps<{ username: string }>()
const emit = defineEmits(['logout'])

const handleLogout = () => {
  emit('logout')
}
</script>

<template>
  <div class="dashboard">
    <h2>欢迎，{{ username }}！</h2>
    <nav>
      <ul>
        <li><a href="#">课程管理</a></li>
        <li><a href="#">学生管理</a></li>
        <li><a href="#">成绩管理</a></li>
      </ul>
    </nav>
    <button @click="handleLogout">登出</button>
  </div>
</template>

<style scoped>
.dashboard {
  text-align: left;
}
nav ul {
  list-style-type: none;
  padding: 0;
}
nav ul li {
  margin-bottom: 10px;
}
nav ul li a {
  text-decoration: none;
  color: #333;
}
nav ul li a:hover {
  color: #4CAF50;
}
button {
  margin-top: 20px;
  padding: 10px;
  background-color: #f44336;
  color: white;
  border: none;
  cursor: pointer;
}
button:hover {
  background-color: #d32f2f;
}
</style>