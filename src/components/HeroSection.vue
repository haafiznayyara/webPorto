<template>
  <section
    id="beranda"
    class="relative min-h-screen flex items-center justify-center overflow-hidden pt-16"
  >
    <!-- Orb glows -->
    <div class="orb w-96 h-96 bg-[#39FF14]/8 top-20 -left-32" />
    <div class="orb w-64 h-64 bg-green-600/10 bottom-20 right-20" />
    <div class="orb w-48 h-48 bg-[#39FF14]/5 top-1/2 right-1/4" />
    <!-- Scan line -->
    <div class="scan-line" />

    <div
      class="max-w-6xl mx-auto px-6 w-full grid md:grid-cols-2 gap-12 items-center"
    >
      <!-- Left -->
      <Motion
        :initial="{ opacity: 0, x: -40 }"
        :animate="{ opacity: 1, x: 0 }"
        :transition="{ duration: 0.8, easing: 'ease-out' }"
      >
        <div>
          <div
            class="font-mono text-[#39FF14] text-xs tracking-widest mb-4 flex items-center gap-2"
          >
            <span class="w-8 h-px bg-[#39FF14]" />
            SELAMAT DATANG
            <span class="cursor-blink">▮</span>
          </div>

          <h1
            class="font-display text-5xl md:text-7xl font-black leading-none mb-6"
          >
            <span class="text-white block">HAAFIZ</span>
            <span class="neon-text block">NAYYARA</span>
            <span
              class="text-white/30 block text-3xl md:text-4xl font-light tracking-wider mt-2"
            >
              Politeknik Negeri Bandung
            </span>
          </h1>

          <p
            class="text-green-100/50 font-mono text-sm leading-relaxed mb-8 max-w-md"
          >
            Saya adalah seorang mahasiswa Teknik Informatika di Politeknik
            Negeri Bandung yang antusias pada pengembangan web dan teknologi
            modern. Berpengalaman dalam membangun aplikasi full-stack dengan
            Laravel, React JS, MySQL, Next JS dan berbagai teknologi terkini.
          </p>

          <div class="flex flex-wrap gap-4">
            <button
              @click="$emit('scroll-to', 'tugas')"
              class="neon-btn font-mono text-xs tracking-widest uppercase px-8 py-3 font-bold rounded-sm"
            >
              Penugasan
            </button>
            <button
              @click="$emit('scroll-to', 'kontak')"
              class="font-mono text-xs tracking-widest uppercase px-8 py-3 border border-[#39FF14]/40 text-[#39FF14]/70 hover:border-[#39FF14] hover:text-[#39FF14] rounded-sm transition-all duration-300"
            >
              Kontak Saya
            </button>
          </div>

          <!-- Stats -->
          <!-- <div class="flex gap-8 mt-12">
            <div v-for="stat in stats" :key="stat.label">
              <div class="neon-text font-display text-2xl font-bold">
                {{ stat.value }}
              </div>
              <div class="text-green-100/40 font-mono text-xs tracking-wider">
                {{ stat.label }}
              </div>
            </div>
          </div> -->
        </div>
      </Motion>

      <!-- Right – terminal card -->
      <Motion
        :initial="{ opacity: 0, x: 40 }"
        :animate="{ opacity: 1, x: 0 }"
        :transition="{ duration: 0.8, delay: 0.2, easing: 'ease-out' }"
      >
        <div class="relative flex justify-center">
          <div class="float-anim w-full max-w-md">
            <div class="glass-card rounded-lg overflow-hidden">
              <!-- Terminal header -->
              <div
                class="flex items-center gap-2 px-4 py-3 border-b border-[#39FF14]/10 bg-[#0c160c]/50"
              >
                <div class="w-3 h-3 rounded-full bg-red-500/70" />
                <div class="w-3 h-3 rounded-full bg-yellow-500/70" />
                <div class="w-3 h-3 rounded-full bg-[#39FF14]/70" />
                <span class="ml-2 font-mono text-xs text-[#39FF14]/40"
                  >~/portfolio/intro.ts</span
                >
              </div>
              <!-- Terminal body -->
              <div class="p-6 font-mono text-xs leading-loose">
                <div class="text-green-600">// Developer Profile</div>
                <div class="mt-2">
                  <span class="text-purple-400">const</span>
                  <span class="text-white"> himakomNextGen </span>
                  <span class="text-[#39FF14]">=</span>
                  <span class="text-white"> {</span>
                </div>
                <div class="pl-4">
                  <div>
                    <span class="text-blue-400">name:</span>
                    <span class="text-yellow-300">"Mohammad Haafiz M.N."</span>,
                  </div>
                  <div>
                    <span class="text-blue-400">role:</span>
                    <span class="text-yellow-300">"Full Stack Developer"</span>,
                  </div>
                  <div>
                    <span class="text-blue-400">location:</span>
                    <span class="text-yellow-300">"Cimahi"</span>,
                  </div>
                  <div>
                    <span class="text-blue-400">skills:</span>
                    <span class="text-white">[</span>
                  </div>
                  <div class="pl-4">
                    <span class="text-yellow-300">"Laravel"</span
                    ><span class="text-white">, </span>
                    <span class="text-yellow-300">"React JS"</span
                    ><span class="text-white">,</span>
                  </div>
                  <div class="pl-4">
                    <span class="text-yellow-300">"MySQL"</span
                    ><span class="text-white">, </span>
                    <span class="text-yellow-300">"Next JS"</span>
                  </div>
                  <div><span class="text-white">],</span></div>
                  <div>
                    <span class="text-blue-400">status:</span>
                    <span class="text-[#39FF14]"
                      >"Siap mengabdi pada HIMAKOM"</span
                    >
                  </div>
                </div>
                <div class="text-white">}</div>
                <div class="mt-3 flex items-center gap-1 text-[#39FF14]/70">
                  <span>$</span>
                  <span class="cursor-blink">▮</span>
                </div>
              </div>
            </div>

            <!-- Floating badges -->
            <div
              class="absolute -top-4 -right-4 glass-card rounded-full px-4 py-2 flex items-center gap-2"
            >
              <div class="w-2 h-2 bg-[#39FF14] rounded-full animate-pulse" />
              <span class="font-mono text-xs text-[#39FF14]">Online</span>
            </div>
            <!-- <div
              class="absolute -bottom-4 -left-4 glass-card rounded-lg px-4 py-2"
            >
              <div class="font-mono text-xs text-green-100/50">Experience</div>
              <div class="neon-text font-display text-lg font-bold">
                
              </div>
            </div> -->
          </div>
        </div>
      </Motion>
    </div>

    <!-- Scroll indicator -->
    <div
      class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 animate-bounce"
    >
      <span class="font-mono text-xs text-[#39FF14]/40 tracking-widest"
        >SCROLL</span
      >
      <div class="w-px h-8 bg-gradient-to-b from-[#39FF14]/40 to-transparent" />
    </div>
  </section>
</template>

<script setup>
import { Motion } from "@motionone/vue";

defineEmits(["scroll-to"]);

const stats = [
  { value: "30+", label: "Projects" },
  { value: "3+", label: "Years Exp" },
  { value: "15+", label: "Clients" },
];
</script>
