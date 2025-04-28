<script setup>
import { ref } from 'vue'
import Menubar from 'primevue/menubar'

const items = ref([
  {
    label: 'Home',
    icon: 'pi pi-home',
    to: '/',
  },
  {
    label: 'About',
    icon: 'pi pi-info-circle',
    to: '#',
  },
  {
    label: 'Contact',
    icon: 'pi pi-envelope',
    to: '#',
  },
])
</script>

<template>
  <header class="p-4 bg-white shadow-sm">
    <div class="flex align-items-center">
      <h1 class="text-xl m-0 font-bold">
        Vuejs3 Skeleton <span class="text-sm text-primary font-normal">by iotexpert</span>
      </h1>
      <div class="flex-grow-1"></div>
      <span class="text-sm text-500 font-semibold">v1.0</span>
    </div>
    <Menubar :model="items" class="border-none surface-0 !mt-2" />
  </header>
</template>
