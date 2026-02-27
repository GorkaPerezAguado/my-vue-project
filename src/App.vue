<script setup>
import { ref } from 'vue'

const name = ref('')
const url = ref('')

const courses = ref([
  { id: 1, name: 'Vue.js Fundamentals', url: 'https://escuela.it/vue-fundamentals' },
  { id: 2, name: 'Advanced Vue Patterns', url: 'https://escuela.it/vue-advanced' },
  { id: 3, name: 'Pinia State Management', url: 'https://escuela.it/pinia' },
  { id: 4, name: 'Vue Router Deep Dive', url: 'https://escuela.it/vue-router' },
  { id: 5, name: 'Testing Vue Apps', url: 'https://escuela.it/vue-testing' },
  { id: 6, name: 'Vite for Vue', url: 'https://escuela.it/vite-vue' },
  { id: 7, name: 'Cypress E2E Testing', url: 'https://escuela.it/cypress' },
  { id: 8, name: 'ESLint & Prettier', url: 'https://escuela.it/eslint-prettier' },
  { id: 9, name: 'Vue Animations', url: 'https://escuela.it/vue-animations' },
  { id: 10, name: 'Vue 3 Composition API', url: 'https://escuela.it/vue3-composition' },
])

const addCourse = () => {
  if (!name.value.trim() || !url.value.trim()) return

  const nextId = courses.value.length
    ? Math.max(...courses.value.map((course) => course.id)) + 1
    : 1

  courses.value.push({
    id: nextId,
    name: name.value.trim(),
    url: url.value.trim(),
  })

  name.value = ''
  url.value = ''
}
</script>

<template>
  <div class="flex flex-col gap-8">
    <header>
      <a href="#" class="btn btn-primary mr-2">Cursos</a>
      <a href="#" class="btn btn-secondary">Nuevo Curso</a>
    </header>

    <form class="card bg-base-100 shadow border border-base-300" @submit.prevent="addCourse">
      <div class="card-body">
        <h2 class="card-title">Nuevo curso</h2>

        <label class="form-control w-full">
          <span class="label-text mb-2">Name</span>
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
          <button type="submit" class="btn btn-primary">Añadir curso</button>
        </div>
      </div>
    </form>

    <div class="overflow-x-auto">
      <table
        class="table table-zebra table-compact w-full rounded-box shadow border border-base-300"
      >
        <thead class="bg-base-200">
          <tr>
            <th>ID</th>
            <th>Nombre</th>
            <th>URL</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="course in courses" :key="course.id" class="hover:bg-base-300">
            <td class="px-4 py-2 whitespace-nowrap">{{ course.id }}</td>
            <td class="px-4 py-2 whitespace-nowrap">{{ course.name }}</td>
            <td class="px-4 py-2 whitespace-nowrap">
              <a :href="course.url" class="btn btn-sm btn-primary" target="_blank" rel="noopener"
                >Ver curso</a
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
