<template>
  <div class="min-h-screen bg-base-200">
    <header class="navbar bg-base-100 border-b border-base-300 px-4 md:px-8">
      <div class="flex-1">
        <RouterLink to="/" class="text-lg font-semibold">Vue Courses</RouterLink>
      </div>
      <nav class="flex gap-2">
        <RouterLink to="/" class="btn btn-ghost btn-sm">Inicio</RouterLink>
        <RouterLink to="/courses" class="btn btn-ghost btn-sm">Cursos</RouterLink>
        <RouterLink to="/about" class="btn btn-ghost btn-sm">About</RouterLink>
      </nav>
    </header>

    <main class="mx-auto w-full max-w-6xl p-4 md:p-8">
      <RouterView />
    </main>
  </div>
</template>

<style scoped>
.router-link-active {
  background-color: color-mix(in oklab, var(--color-primary) 15%, transparent);
  color: var(--color-primary);
}
</style>
