<script setup>
import { RouterView } from 'vue-router'
import AppFooter from './components/layout/AppFooter.vue'
import AppSidebar from './components/layout/AppSidebar.vue'
</script>

<template>
  <div class="min-h-screen flex bg-gray-50 relative">
    <AppSidebar />
    <div class="flex-1 flex flex-col pl-64">
      <main class="flex-1 px-4 py-3">
        <RouterView />
      </main>
      <AppFooter />
    </div>
  </div>
</template>
