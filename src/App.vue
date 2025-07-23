<script setup>
import { RouterView } from 'vue-router'
import { ref } from 'vue'

const isDropdownOpen = ref(false)

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value
}
</script>

<template>
  <header>
    <div class="logo-container">
      <img alt="Vue logo" class="logo" src="@/assets/logo.png" width="100" height="100" />
      <h1 class="header-title">Taira的創意園地</h1>
    </div>
    <div class="dropdown-container">
      <button @click="toggleDropdown" class="dropdown-button">選單</button>
      <ul v-if="isDropdownOpen" class="dropdown-menu">
        <li>選項 1</li>
        <li>選項 2</li>
        <li>選項 3</li>
        <li>選項 4</li>
        <li>選項 5</li>
      </ul>
    </div>
  </header>

  <main>
    <div class="section section-1">自我介紹</div>
    <div class="section section-2">自我介紹2</div>
    <div class="section section-3">作品1</div>
    <div class="section section-4">作品2</div>
    <div class="section section-5">作品3</div>
    <div class="section section-6">作品4</div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #ffffff;
  z-index: 1000;
  padding: 0.5rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-container {
  display: flex;
  align-items: center;
}

.header-title {
  margin-left: 30px;
  font-size: 1.5rem;
  font-weight: bold;
  color: #000000;
}

.logo {
  display: block;
  /* Adjust margin as needed, setting to 0 for flex alignment */
  margin: 0;
}

.dropdown-container {
  position: relative;
}

.dropdown-button {
  padding: 8px 16px;
  border: 1px solid #ccc;
  background-color: #f0f0f0;
  cursor: pointer;
  border-radius: 4px;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  right: 0;
  background-color: white;
  border: 1px solid #ccc;
  list-style: none;
  padding: 0.5rem 0;
  margin: 0.25rem 0 0;
  min-width: 160px;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}

.dropdown-menu li {
  padding: 0.5rem 1rem;
  cursor: pointer;
}

.dropdown-menu li:hover {
  background-color: #f0f0f0;
}

main {
  padding-top: 126px; /* Adjusted to ensure 20px gap below fixed header */
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.section {
  border: 2px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.2rem;
  min-height: 850px; /* Example height */
}

/* Example background colors for visualization */
.section-1 { background-color: #f2f2f2; }
.section-2 { background-color: #e6e6e6; }
.section-3 { background-color: #d9d9d9; }
.section-4 { background-color: #cccccc; }
.section-5 { background-color: #bfbfbf; }
.section-6 { background-color: #b3b3b3; }

</style>

