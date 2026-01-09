<template>
  <section class="animate-fadeIn flex flex-col items-center justify-center">
    <h2 class="text-3xl font-bold text-slate-800 mb-6 text-center">
      Publications & Certifications
    </h2>
    <div class="h-1 w-20 bg-blue-600 rounded my-6 "></div>
    <div class="space-y-4 pt-8">
      <div 
        v-for="(item, index) in items" 
        :key="index" 
        class="bg-white border-l-4 border-blue-600 pl-6 py-3 hover:bg-slate-50 transition-colors"
      >
        <div class="flex items-stretch justify-between gap-4">
          <div class="flex-1">
            <div class="flex items-center gap-2 mb-2">
              <span 
                :class="[
                  'px-3 py-1 rounded-full text-xs font-medium',
                  item.type === 'certification' 
                    ? 'bg-green-100 text-green-700' 
                    : 'bg-purple-100 text-purple-700'
                ]"
              >
                {{ item.type === 'certification' ? 'Certification' : 'Publication' }}
              </span>
              <span class="text-sm text-slate-500">{{ item.date }}</span>
            </div>
            <h3 class="text-lg font-semibold text-slate-800 mb-1">
              {{ item.title }}
            </h3>
            <p class="text-slate-600">{{ item.issuer || item.publisher }}</p>
          </div>
          <!-- <div class="flex flex-col justify-center items-center">
            <a 
              :href="item.link"
              target="_blank"
              rel="noopener noreferrer"
              class="text-blue-600 hover:text-blue-700 font-medium whitespace-nowrap cursor-pointer"
            >
              View →
            </a>
          </div> -->
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>

defineProps({
  items: {
    type: Array,
    required: true
  }
})
</script>
