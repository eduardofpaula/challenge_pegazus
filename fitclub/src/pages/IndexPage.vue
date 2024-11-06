<script setup lang="ts">
const store = useStore()
</script>
<template>
  <header class="h-screen bg-gradient-to-tr from-cinza1 via-cinza2 to-laranja2">
    <div class="flex items-center justify-between px-6 py-4 mx-60">
      <div>
        <img src="@/assets/logo.png" alt="logo" class="w-100" />
      </div>

      <nav class="flex flex-grow justify-center mt-8">
        <ul class="flex space-x-6 text-branco">
          <li>
            <a href="#home" class="navButton">Home</a>
          </li>
          <li>
            <a href="#about" class="navButton">Program</a>
          </li>
          <li>
            <a href="#services" class="navButton">Service</a>
          </li>
          <li>
            <a href="#contact" class="navButton">About</a>
          </li>
          <li>
            <a href="#community" class="navButton">Community</a>
          </li>
        </ul>
      </nav>

      <a href="#dourado" class="goldButton">Join Now</a>
    </div>
  </header>
</template>

<style scoped>
.navButton {
  @apply hover:text-laranja2 transition duration-300;
}

.goldButton {
  background-color: #f9ac54;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 16px;
  font-weight: bold;
  border-radius: 10px;
  transition:
    background-color 0.3s ease,
    transform 0.3s ease;
  cursor: pointer;
}
</style>
