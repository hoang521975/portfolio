<template>
  <nav class="fixed flex flex-col gap-3 px-1 justify-center">
    <!-- <div class=""> -->
      <button
        v-for="section in sections"
        :key="section.id"
        @click="$emit('update:activeSection', section.id)"
        :class="[
          'w-full flex items-center gap-4 px-6 py-4 rounded-lg text-left transition-all',
          activeSection === section.id
            ? 'bg-blue-600 text-white shadow-md'
            : 'text-slate-700 hover:bg-slate-100'
        ]"
      >
        <component :is="section.icon" :size="22" />
        <span class="font-medium text-base">
          {{ section.label }}
        </span>
      </button>
    <!-- </div> -->
  </nav>
</template>

<script setup>
defineProps({
  sections: {
    type: Array,
    required: true
  },
  activeSection: {
    type: String,
    required: true
  }
})

defineEmits(['update:activeSection'])
</script>