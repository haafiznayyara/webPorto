<template>
  <nav
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-500"
    :class="
      scrolled
        ? 'bg-[#050a05]/90 backdrop-blur-xl border-b border-[#39FF14]/10 shadow-lg shadow-[#39FF14]/5'
        : 'bg-transparent'
    "
  >
    <div class="max-w-6xl mx-auto px-6 h-16 flex items-center justify-between">
      <!-- Logo -->
      <div class="font-display font-bold text-xl tracking-wider">
        <span class="text-white mr-1">Haafiz's</span>
        <!-- <span class="neon-text">.</span> -->
        <span class="neon-text text-sm font-mono">space</span>
      </div>

      <!-- Desktop Menu -->
      <div class="hidden md:flex items-center gap-8">
        <a
          v-for="item in navItems"
          :key="item.id"
          href="javascript:void(0)"
          @click="$emit('scroll-to', item.id)"
          class="font-mono text-xs tracking-widest uppercase transition-all duration-300 hover:text-[#39FF14] relative group"
          :class="
            activeSection === item.id
              ? 'text-[#39FF14] [text-shadow:0_0_8px_rgba(57,255,20,0.5)]'
              : 'text-green-100/60'
          "
        >
          {{ item.label }}
          <span
            class="absolute -bottom-1 left-0 h-px bg-[#39FF14] transition-all duration-300"
            :class="
              activeSection === item.id ? 'w-full' : 'w-0 group-hover:w-full'
            "
          />
        </a>
        <button
          @click="$emit('scroll-to', 'kontak')"
          class="neon-btn font-mono text-xs tracking-widest uppercase px-5 py-2 rounded-sm font-bold"
        >
          Kontak
        </button>
      </div>

      <!-- Hamburger -->
      <button
        @click="mobileOpen = !mobileOpen"
        class="md:hidden text-[#39FF14] p-2"
      >
        <div
          class="w-5 h-0.5 bg-[#39FF14] mb-1.5 transition-all duration-300"
          :class="mobileOpen ? 'rotate-45 translate-y-2' : ''"
        />
        <div
          class="w-5 h-0.5 bg-[#39FF14] mb-1.5 transition-all duration-300"
          :class="mobileOpen ? 'opacity-0' : ''"
        />
        <div
          class="w-5 h-0.5 bg-[#39FF14] transition-all duration-300"
          :class="mobileOpen ? '-rotate-45 -translate-y-2' : ''"
        />
      </button>
    </div>

    <!-- Mobile Menu -->
    <Transition name="slide-down">
      <div
        v-if="mobileOpen"
        class="md:hidden bg-[#050a05]/95 backdrop-blur-xl border-b border-[#39FF14]/10 py-4"
      >
        <div class="flex flex-col items-center gap-4">
          <a
            v-for="item in navItems"
            :key="item.id"
            href="javascript:void(0)"
            @click="
              $emit('scroll-to', item.id);
              mobileOpen = false;
            "
            class="font-mono text-xs tracking-widest uppercase transition-colors duration-300"
            :class="
              activeSection === item.id ? 'text-[#39FF14]' : 'text-green-100/60'
            "
          >
            {{ item.label }}
          </a>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script setup>
import { ref } from "vue";

defineProps({
  scrolled: Boolean,
  activeSection: String,
});

defineEmits(["scroll-to"]);

const mobileOpen = ref(false);

const navItems = [
  { id: "beranda", label: "Beranda" },
  { id: "profil", label: "Profil dan Skill" },
  { id: "portofolio", label: "Portofolio" },
  { id: "tugas", label: "Penugasan" },
];
</script>
