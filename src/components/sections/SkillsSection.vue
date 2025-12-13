<template>
  <div class="animate-fadeIn flex flex-col items-center">
    <h2 class="text-3xl font-bold text-slate-800 mb-2">Technical Skills</h2>
    <div class="h-1 w-20 bg-blue-600 rounded mb-6"></div>
    
    <div class="grid md:grid-cols-2 gap-6 mb-4 md:mb-8 pt-4 md:pt-8">
      <div 
        v-for="(skillGroup, index) in skills" 
        :key="index" 
        class="bg-white border-l-4 border-blue-600 pl-6 py-3 hover:bg-slate-50 transition-colors"
      >
        <h3 class="text-xl font-semibold text-slate-800 mb-4">
          {{ skillGroup.category }}
        </h3>
        <div class="flex flex-wrap gap-2">
          <span 
            v-for="(skill, idx) in skillGroup.items" 
            :key="idx"
            class="px-4 py-2 bg-blue-50 text-blue-700 rounded-lg text-sm font-medium hover:bg-blue-100 transition-colors"
          >
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  skills: {
    type: Array,
    required: true
  }
})
</script>