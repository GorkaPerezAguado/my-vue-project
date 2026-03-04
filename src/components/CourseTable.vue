<script setup>
defineProps({
  courses: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <div class="overflow-x-auto">
    <table class="table table-zebra table-compact w-full rounded-box shadow border border-base-300">
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
            <a :href="course.url" class="btn btn-sm btn-primary" target="_blank" rel="noopener">
              Ver curso
            </a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
