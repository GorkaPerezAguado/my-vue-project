<script setup>
import { ref } from 'vue'
import CourseForm from '../components/CourseForm.vue'
import CourseTable from '../components/CourseTable.vue'

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

// El padre recibe los datos del formulario y completa el id.
const addCourse = ({ name, url }) => {
  const nextId = courses.value.length
    ? Math.max(...courses.value.map((course) => course.id)) + 1
    : 1

  courses.value.push({
    id: nextId,
    name,
    url,
  })
}
</script>

<template>
  <section class="flex flex-col gap-8">
    <header>
      <h1 class="text-2xl font-bold">Catálogo de cursos</h1>
      <p class="text-base-content/70">Gestiona cursos y enlaces desde esta vista.</p>
    </header>

    <CourseForm @add-course="addCourse" />
    <CourseTable :courses="courses" />
  </section>
</template>
