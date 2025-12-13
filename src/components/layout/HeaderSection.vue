<template>
  <header class="bg-white shadow-md">
    <div class="max-w-7xl mx-auto px-4 py-12 justify-center">
      <div class="flex flex-col md:flex-row items-center justify-center gap-8">
        <!-- MOBILE MENU SLOT (LEFT of avatar) -->
        <slot name="menu"></slot>
        <!-- Avatar -->
        <img 
          :src="personal.image" 
          :alt="personal.name"
          class="w-40 h-40 rounded-full object-cover border-4 border-blue-500 shadow-lg"
        />
        
        <!-- Name and Title -->
        <div class="text-center md:text-left">
          <h1 class="text-4xl font-bold text-slate-800 mb-2">{{ personal.name }}</h1>
          <p class="text-xl text-slate-600">{{ personal.title }}</p>
        </div>
        
        <!-- Contact Info - Vertical List -->
        <div class="flex flex-col gap-3 text-sm md:ml-auto">
          <a 
            :href="`mailto:${personal.email}`" 
            class="flex items-center gap-2 text-slate-600 hover:text-blue-600 transition-colors"
          >
            <Mail :size="18" />
            <span>{{ personal.email }}</span>
          </a>
          <div class="flex items-center gap-2 text-slate-600">
            <Phone :size="18" />
            <span>{{ personal.phone }}</span>
          </div>
          <div class="flex items-center gap-2 text-slate-600">
            <MapPin :size="18" />
            <span>{{ personal.location }}</span>
          </div>

        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { Mail, Phone, MapPin } from 'lucide-vue-next'

defineProps({
  personal: {
    type: Object,
    required: true
  }
})
</script>