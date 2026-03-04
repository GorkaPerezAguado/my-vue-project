<script setup>
import { ref } from 'vue'

// Emitimos un evento al componente padre cuando se crea un curso valido.
const emit = defineEmits(['add-course'])

const name = ref('')
const url = ref('')

const submit = () => {
  const trimmedName = name.value.trim()
  const trimmedUrl = url.value.trim()

  if (!trimmedName || !trimmedUrl) return

  emit('add-course', {
    name: trimmedName,
    url: trimmedUrl,
  })

  name.value = ''
  url.value = ''
}
</script>

<template>
  <form class="card bg-base-100 shadow border border-base-300" @submit.prevent="submit">
    <div class="card-body">
      <h2 class="card-title">Nuevo curso</h2>

      <label class="form-control w-full">
        <span class="label-text mb-2">Nombre</span>
        <input
          v-model="name"
          type="text"
          placeholder="Ej. Vue 3 Composition API"
          class="input input-bordered w-full"
        />
      </label>

      <label class="form-control w-full">
        <span class="label-text mb-2">URL</span>
        <input
          v-model="url"
          type="url"
          placeholder="https://..."
          class="input input-bordered w-full"
        />
      </label>

      <div class="card-actions justify-end">
        <button type="submit" class="btn btn-primary">Anadir curso</button>
      </div>
    </div>
  </form>
</template>
