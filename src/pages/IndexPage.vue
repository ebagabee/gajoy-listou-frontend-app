<template>
  <q-page class="q-pa-md">
    <h4>Minha Lista de Compras</h4>

    <div class="q-gutter-y-md">
      <q-input v-model="newItem" label="Novo Item" outlined @keyup.enter="addItem">
        <template #append>
          <q-btn round dense flat icon="add" @click="addItem" :disable="!newItem" />
        </template>
      </q-input>

      <q-list bordered separator>
        <q-item v-for="(item, index) in items" :key="index" clickable v-ripple>
          <q-item-section>
            {{ item.text }}
          </q-item-section>

          <q-item-section side>
            <q-btn
              flat
              round
              dense
              icon="delete"
              color="negative"
              @click.stop="removeItem(index)"
            />
          </q-item-section>
        </q-item>
      </q-list>
    </div>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { Preferences } from '@capacitor/preferences'

const newItem = ref('')
const items = ref([])

onMounted(async () => {
  await loadItems()
})

async function loadItems() {
  const storedItems = await Preferences.get({ key: 'shoppingItems' })
  if (storedItems && storedItems.value) {
    items.value = JSON.parse(storedItems.value)
  }
}

async function saveItems() {
  await Preferences.set({
    key: 'shoppingItems',
    value: JSON.stringify(items.value),
  })
}

async function addItem() {
  if (newItem.value.trim()) {
    items.value.push({
      text: newItem.value.trim(),
      completed: false,
      timestamp: new Date().getTime(),
    })
    newItem.value = ''
    await saveItems()
  }
}

async function removeItem(index) {
  items.value.splice(index, 1)
  await saveItems()
}
</script>
