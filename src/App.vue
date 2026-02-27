<script setup>
const courses = [
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
]
</script>

<template>
  <div class="flex flex-col gap-8">
    <header>
      <a href="#" class="btn btn-primary mr-2">Cursos</a>
      <a href="#" class="btn btn-secondary">Nuevo Curso</a>
    </header>

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
          <tr
            v-for="course in courses"
            :key="course.id"
            :class="course.id === 2 ? 'hover:bg-base-300' : ''"
          >
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
