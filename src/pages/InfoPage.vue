<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Hector Lugo',
  avatar:
    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTEP8qqnnnbzLHgHwn5QBrVvzSvF-XH6jebsQ&s',
  about: 'Passionate about securing cloud infrastructure and learning new technologies.',
  skills: ['Cloud Security', 'Network Security', 'Python', 'JavaScript', 'Tailwind CSS'],
  email: 'haze.lugo@gmail.com',
  location: 'McAllen, TX',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="self-starttext-sm mt-8 text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-green-400 hover:underline"
    >
      ← Back to Links
    </RouterLink>

    <!-- Profile Card -->
    <div
      class="w-full max-w-lg rounded-2xl border border-gray-700 bg-gray-800 p-6 shadow-xl shadow-green-900/50 sm:p-8"
    >
      <!-- Header -->
      <div class="mb-6 flex flex-col items-center text-center sm:flex-row sm:text-left">
        <div
          class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-green-400 sm:mr-6 sm:mb-0"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>
        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-white">{{ bio.name }}</h1>
          <p class="text-sm text-gray-400">📍 {{ bio.location }}</p>
        </div>
      </div>

      <!-- About Section -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">About</h2>
        <p class="leading-relaxed text-gray-300">{{ bio.about }}</p>
      </div>

      <!-- Skills Section -->
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Skills</h2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full bg-green-900/50 px-3 py-1 text-sm text-green-300"
          >
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </main>
</template>
