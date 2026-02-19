<template>
  <footer class="relative border-t border-[#39FF14]/10 py-12 overflow-hidden">
    <div class="max-w-6xl mx-auto px-6">
      <div class="flex flex-col md:flex-row items-center justify-between gap-4">
        <div class="font-mono text-xs text-green-100/30">
          © {{ currentYear }} Mohammad Haafiz. All rights reserved.
        </div>
        <button
          @click="$emit('scroll-to', 'beranda')"
          class="font-mono text-xs text-[#39FF14]/40 hover:text-[#39FF14] transition-colors flex items-center gap-2 group"
        >
          Kembali ke Atas
          <span
            class="group-hover:-translate-y-1 transition-transform inline-block"
            >↑</span
          >
        </button>
      </div>
    </div>
  </footer>
</template>

<script setup>
defineEmits(["scroll-to"]);

const currentYear = new Date().getFullYear();
</script>
