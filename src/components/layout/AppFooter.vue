<template>
  <footer class="bg-white p-4 text-center mt-auto">
    <div class="max-w-7xl mx-auto">
      <p class="text-gray-600">&copy; {{ currentYear }} Your Company Name. All rights reserved.</p>
    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear()
</script>
