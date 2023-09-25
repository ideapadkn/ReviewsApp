<script setup></script>

<template>
  <header class="mb-8">
    <div class="bg-gray-900">
      <div class="container mx-auto">
        <div class="flex justify-between items-center h-[80px]">
          <h2 class="text-green-500 text-3xl font-bold">Rewiew UI</h2>
          <nav class="flex gap-8">
            <router-link active-class="active" class="text-white text-[18px] font-semibold" to="/">Home</router-link>
            <router-link active-class="active" class="text-white text-[18px] font-semibold"
              to="/about">About</router-link>
          </nav>
        </div>
      </div>
    </div>
  </header>
</template>

<style>
.active {
  color: rgb(34 197 94);
}
</style>