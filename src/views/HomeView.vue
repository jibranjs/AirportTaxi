<script setup>
import Card from 'primevue/card'
import Button from 'primevue/button'
import InputText from 'primevue/inputtext'
import DataTable from 'primevue/datatable'
import Column from 'primevue/column'
import { Icon } from '@iconify/vue'
import { ref } from 'vue'

const products = ref([
  { id: 1, name: 'Laptop Pro', category: 'Electronics', price: 1299, status: 'In Stock' },
  { id: 2, name: 'Wireless Mouse', category: 'Accessories', price: 49, status: 'Low Stock' },
  { id: 3, name: 'Gaming Monitor', category: 'Electronics', price: 599, status: 'Out of Stock' },
  { id: 4, name: 'Mechanical Keyboard', category: 'Accessories', price: 159, status: 'In Stock' },
  { id: 5, name: 'USB-C Hub', category: 'Accessories', price: 79, status: 'In Stock' },
])
</script>

<template>
  <div class="!space-y-6">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
      <!-- Stats Cards -->
      <Card class="shadow-sm">
        <template #title>
          <div class="flex items-center gap-2">
            <Icon icon="mdi:account-group" class="text-xl" />
            <span>Users</span>
          </div>
        </template>
        <template #content>
          <div class="text-2xl font-bold">1,234</div>
        </template>
      </Card>

      <Card class="shadow-sm">
        <template #title>
          <div class="flex items-center gap-2">
            <Icon icon="mdi:chart-line" class="text-xl" />
            <span>Revenue</span>
          </div>
        </template>
        <template #content>
          <div class="text-2xl font-bold">$45,678</div>
        </template>
      </Card>

      <Card class="shadow-sm">
        <template #title>
          <div class="flex items-center gap-2">
            <Icon icon="mdi:shopping" class="text-xl" />
            <span>Orders</span>
          </div>
        </template>
        <template #content>
          <div class="text-2xl font-bold">856</div>
        </template>
      </Card>

      <Card class="shadow-sm">
        <template #title>
          <div class="flex items-center gap-2">
            <Icon icon="mdi:trending-up" class="text-xl" />
            <span>Growth</span>
          </div>
        </template>
        <template #content>
          <div class="text-2xl font-bold">23.5%</div>
        </template>
      </Card>
    </div>

    <!-- PrimeVue Components Demo -->
    <Card class="shadow-sm">
      <template #title>
        <div class="flex items-center gap-2">
          <Icon icon="mdi:puzzle" class="text-xl" />
          <span>PrimeVue Components</span>
        </div>
      </template>
      <template #content>
        <div class="space-y-2">
          <div class="flex flex-wrap gap-4">
            <Button label="Primary" />
            <Button label="Secondary" severity="secondary" />
            <Button label="Success" severity="success" />
            <Button label="Info" severity="info" />
          </div>
          <div class="flex flex-wrap gap-4 !mt-4">
            <span class="p-input-icon-left">
              <InputText placeholder="Search" />
            </span>
            <span class="p-input-icon-right">
              <InputText placeholder="Loading..." />
            </span>
          </div>
        </div>
      </template>
    </Card>

    <!-- PrimeVue + Iconify Integration -->
    <Card class="shadow-sm">
      <template #title>
        <div class="flex items-center gap-2">
          <Icon icon="mdi:puzzle-plus" class="text-xl" />
          <span>PrimeVue + Iconify Integration</span>
        </div>
      </template>
      <template #content>
        <div class="flex flex-wrap gap-4">
          <Button>
            <Icon icon="mdi:content-save" class="mr-2" />
            <span>Save</span>
          </Button>
          <Button severity="success">
            <Icon icon="mdi:check-circle" class="mr-2" />
            <span>Confirm</span>
          </Button>
          <Button severity="danger">
            <Icon icon="mdi:trash-can" class="mr-2" />
            <span>Delete</span>
          </Button>
          <Button severity="warning">
            <Icon icon="mdi:alert" class="mr-2" />
            <span>Warning</span>
          </Button>
        </div>
      </template>
    </Card>

    <!-- Vue-related Icons -->
    <Card class="shadow-sm">
      <template #title>
        <div class="flex items-center gap-2">
          <Icon icon="mdi:information" class="text-xl" />
          <span>Iconify Icons</span>
        </div>
      </template>
      <template #content>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
          <div class="flex flex-col items-center p-4 bg-gray-50 rounded-lg">
            <Icon icon="logos:vue" class="text-4xl mb-2" />
            <span class="text-sm">Vue.js</span>
          </div>
          <div class="flex flex-col items-center p-4 bg-gray-50 rounded-lg">
            <Icon icon="simple-icons:primevue" class="text-4xl mb-2 text-green-500" />
            <span class="text-sm">PrimeVue</span>
          </div>
          <div class="flex flex-col items-center p-4 bg-gray-50 rounded-lg">
            <Icon icon="logos:vitejs" class="text-4xl mb-2" />
            <span class="text-sm">Vite</span>
          </div>
          <div class="flex flex-col items-center p-4 bg-gray-50 rounded-lg">
            <Icon icon="logos:pinia" class="text-4xl mb-2" />
            <span class="text-sm">Pinia</span>
          </div>
        </div>
        <p class="mt-4 text-gray-600">
          Iconify provides access to over 100,000 icons from various icon sets.
          <a
            href="https://icon-sets.iconify.design"
            target="_blank"
            class="hover:underline"
          >
            Browse all icons
            <Icon icon="mdi:external-link" class="inline" />
          </a>
        </p>
      </template>
    </Card>

    <!-- Product Table -->
    <Card class="shadow-sm">
      <template #title>
        <div class="flex items-center gap-2">
          <Icon icon="mdi:table" class="text-xl" />
          <span>Product Inventory</span>
        </div>
      </template>
      <template #content>
        <DataTable :value="products" stripedRows>
          <Column field="id" header="ID" sortable></Column>
          <Column field="name" header="Name" sortable></Column>
          <Column field="category" header="Category" sortable></Column>
          <Column field="price" header="Price" sortable>
            <template #body="slotProps">
              ${{ slotProps.data.price }}
            </template>
          </Column>
          <Column field="status" header="Status" sortable>
            <template #body="slotProps">
              <span :class="{
                'bg-green-100 text-green-700': slotProps.data.status === 'In Stock',
                'bg-yellow-100 text-yellow-700': slotProps.data.status === 'Low Stock',
                'bg-red-100 text-red-700': slotProps.data.status === 'Out of Stock'
              }" class="px-2 py-1 rounded-full text-sm">
                {{ slotProps.data.status }}
              </span>
            </template>
          </Column>
        </DataTable>
      </template>
    </Card>
  </div>
</template>

<style scoped>
</style>
