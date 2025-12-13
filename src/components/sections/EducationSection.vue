<template>
  <section class="animate-fadeIn flex flex-col w-full">
    <div class="flex flex-col items-center mb-6">
      <h2 class="text-3xl font-bold text-slate-800">
        Education
      </h2>

      <div class="h-1 w-20 bg-blue-600 rounded mt-4"></div>
    </div>

    <div class="space-y-4 pt-8 w-full">
      <div
        v-for="(edu, index) in education"
        :key="index"
        class="w-full bg-white border-l-4 border-blue-600 pl-6 py-4 hover:bg-slate-50 transition-colors"
      >
        <h3 class="text-xl font-bold text-slate-800 mb-2">{{ edu.degree }}</h3>
        <p class="text-lg text-slate-700 mb-1">{{ edu.institution }}</p>
        <div class="flex items-center gap-4 text-slate-600 mb-4">
          <span class="flex items-center">
            <MapPin :size="16" />
            {{ edu.location }}
          </span>
          <span>{{ edu.date }}</span>
        </div>
        <ul class="space-y-2">
          <li 
            v-for="(achievement, idx) in edu.achievements" 
            :key="idx" 
            class="text-slate-600 flex items-start gap-2"
          >
            <span class="text-blue-600 mt-1">•</span>
            {{ achievement }}
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>

defineProps({
  education: {
    type: Array,
    required: true
  }
})
</script>