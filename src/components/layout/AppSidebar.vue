<script setup>
import { ref } from 'vue'
import profilePhoto from '@/assets/images/user.png'
import Button from 'primevue/button'

const currentUser = ref({
  name: 'John Doe',
  avatar: profilePhoto
})

const menuItems = ref([
  {
    label: 'Dashboard',
    icon: 'mdi:view-dashboard',
    to: '/'
  },
  {
    label: 'Users',
    icon: 'mdi:account-group',
    to: '/users'
  },
  {
    label: 'Analytics',
    icon: 'mdi:chart-bar',
    to: '/analytics'
  },
  {
    label: 'Settings',
    icon: 'mdi:cog',
    to: '/settings'
  }
])
</script>

<template>
  <aside class="fixed top-0 left-0 w-64 bg-white shadow-sm flex flex-col h-screen px-4 overflow-y-auto z-40">
    <div class="!my-2 text-center">
      <h1 class="text-sm uppercase bg-gray-200 rounded-lg p-2 font-bold">Vuejs3 Skeleton</h1>
    </div>

    <!-- Navigation Menu -->
    <nav class="flex-1">
      <ul class="!space-y-1">
        <li v-for="item in menuItems" :key="item.label">
          <router-link
            :to="item.to"
            class="flex items-center gap-2 p-3 rounded-lg hover:bg-gray-100 transition-colors"
            :class="{ 'bg-gray-100': $route.path === item.to }"
          >
            <Icon :icon="item.icon" class="text-md" />
            <span>{{ item.label }}</span>
          </router-link>
        </li>
      </ul>
    </nav>

    <!-- User Profile Section -->
    <div class="pb-4">
      <div class="flex items-center gap-2 !mb-2 bg-gray-100 rounded-lg px-2 py-1 border-1 border-gray-300">
        <img
          :src="currentUser.avatar"
          class="w-10 h-10 rounded-full border-2 border-white shadow-sm"
          :alt="currentUser.name"
        >
        <div>
          <div class="font-semibold text-sm text-gray-800">{{ currentUser.name }}</div>
          <div class="text-xs text-gray-600">Administrator</div>
        </div>
      </div>
      <div class="flex gap-2">
        <Button
          class="flex-1 !text-xs !bg-white !text-black !border-black !p-1 hover:!bg-gray-300"
          @click="() => {}"
        >
          <Icon icon="mdi:cog" class="mr-2" />
          Settings
        </Button>
        <Button
          class="flex-1 !text-xs !bg-white !text-black !border-black !p-1 hover:!bg-gray-300"
          @click="() => {}"
        >
          <Icon icon="mdi:logout" class="mr-2" />
          Logout
        </Button>
      </div>
    </div>
  </aside>
</template>