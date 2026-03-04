<template>
  <section class="hero rounded-box bg-base-100 border border-base-300 shadow">
    <div class="hero-content py-16 text-center">
      <div class="max-w-xl">
        <h1 class="text-4xl font-bold">Inicio</h1>
        <p class="py-4 text-base-content/75">
          Esta app usa Vue Router para separar vistas reales. Desde aqui puedes navegar al listado
          de cursos y a la pagina about.
        </p>
        <div class="flex justify-center gap-3">
          <RouterLink to="/courses" class="btn btn-primary">Ir a cursos</RouterLink>
          <RouterLink to="/about" class="btn btn-outline">Ir a about</RouterLink>
        </div>
      </div>
    </div>
  </section>
</template>
