<template>
  <section id="profil" class="relative py-32 overflow-hidden">
    <div class="orb w-72 h-72 bg-[#39FF14]/6 bottom-0 right-0" />

    <div class="max-w-6xl mx-auto px-6">
      <!-- Section header -->
      <Motion
        :initial="{ opacity: 0, y: 30 }"
        :inView="{ opacity: 1, y: 0 }"
        :transition="{ duration: 0.6 }"
      >
        <div class="flex items-center gap-4 mb-16">
          <span class="font-mono text-[#39FF14] text-xs tracking-widest"
            >02.</span
          >
          <h2 class="font-display text-4xl font-black text-white">
            PROFIL <span class="neon-text">&</span> SKILL
          </h2>
          <div
            class="flex-1 h-px bg-gradient-to-r from-[#39FF14]/30 to-transparent"
          />
        </div>
      </Motion>

      <!-- Profile: Photo + Description -->
      <div class="flex flex-col md:flex-row gap-8 mb-20 items-start">
        <!-- Photo Avatar -->
        <Motion
          :initial="{ opacity: 0, scale: 0.9 }"
          :inView="{ opacity: 1, scale: 1 }"
          :transition="{ duration: 0.6, delay: 0.1 }"
        >
          <div class="relative group mx-auto md:mx-0 flex-shrink-0 mt-8">
            <!-- Photo frame -->
            <div
              class="relative w-36 h-36 rounded-full overflow-hidden glass-card border-2 border-[#39FF14]/30 group-hover:border-[#39FF14]/60 transition-all duration-300 group-hover:shadow-[0_0_30px_rgba(57,255,20,0.3)]"
            >
              <img
                src="/src/assets/porto/hapis.jpeg"
                alt="Profile Photo"
                class="w-full h-full object-cover grayscale-[30%] group-hover:grayscale-0 transition-all duration-500"
              />
              <!-- Subtle gradient overlay -->
              <div
                class="absolute inset-0 bg-gradient-to-t from-[#050a05]/40 to-transparent"
              />
            </div>

            <!-- Decorative ring -->
            <div
              class="absolute inset-0 w-36 h-36 rounded-full border border-[#39FF14]/10 animate-pulse"
              style="animation-duration: 3s"
            />

            <!-- Status badge -->
            <div class="absolute -bottom-2 left-1/2 -translate-x-1/2">
              <div
                class="glass-card rounded-full px-3 py-1.5 flex items-center gap-1.5 border border-[#39FF14]/30"
              >
                <div
                  class="w-1.5 h-1.5 bg-[#39FF14] rounded-full animate-pulse"
                />
                <span class="font-mono text-xs text-[#39FF14]">Online</span>
              </div>
            </div>
          </div>
        </Motion>

        <!-- About Description -->
        <Motion
          :initial="{ opacity: 0, x: 30 }"
          :inView="{ opacity: 1, x: 0 }"
          :transition="{ duration: 0.7, delay: 0.2 }"
        >
          <div>
            <div
              class="font-mono text-[#39FF14]/40 text-xs tracking-widest mb-4"
            >
              // TENTANG SAYA
            </div>

            <h3 class="font-display text-3xl font-bold text-white mb-4">
              Halo! Saya
              <span class="neon-text">Mohammad Haafiz Mawla Nayyara</span>
            </h3>

            <div class="space-y-4 text-green-100/70 leading-relaxed">
              <p>
                Seorang mahasiswa
                <span class="text-[#39FF14] font-semibold"
                  >Teknik Informatika</span
                >
                yang antusias terhadap hal-hal yang berbau logika. Saya senang
                memecahkan masalah kompleks dan menciptakan solusi yang efisien.
                Dengan pengalaman dalam pengembangan web, sangat membantu saya
                untuk memecahkan berbagai tantangan teknologi.
              </p>

              <p class="text-green-100/60">
                Saya juga sangat tertarik terhadap suatu organisasi, karena
                dengan organisasi saya bisa belajar banyak hal baru, bertemu
                dengan orang-orang hebat, dan tentunya bisa menambah pengalaman
                saya dalam bekerja sama dengan orang lain. Dengan adanya
                <span class="text-[#39FF14] font-semibold">HIMAKOM</span>
                , saya harap saya bisa mengembangkan kemampuan saya, baik hard
                skill maupun soft skill.
              </p>

              <p
                class="text-green-100/50 text-sm italic border-l-2 border-[#39FF14]/30 pl-4"
              >
                "Kalo malas besok ajah."
              </p>
            </div>
          </div>
        </Motion>
      </div>

      <!-- Skills & Interests Cards -->
      <div>
        <Motion
          :initial="{ opacity: 0, y: 20 }"
          :inView="{ opacity: 1, y: 0 }"
          :transition="{ duration: 0.6 }"
        >
          <div class="flex items-center gap-4 mb-8">
            <div
              class="flex-1 h-px bg-gradient-to-r from-transparent to-[#39FF14]/20"
            />
            <span class="font-mono text-[#39FF14]/40 text-xs tracking-widest"
              >KEAHLIAN & MINAT</span
            >
            <div
              class="flex-1 h-px bg-gradient-to-l from-transparent to-[#39FF14]/20"
            />
          </div>
        </Motion>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5">
          <Motion
            v-for="(item, idx) in skillsInterests"
            :key="item.title"
            :initial="{ opacity: 0, y: 40 }"
            :inView="{ opacity: 1, y: 0 }"
            :transition="{ duration: 0.5, delay: idx * 0.08 }"
          >
            <div
              class="skill-card glass-card rounded-xl p-6 group cursor-default h-full border border-[#39FF14]/10 hover:border-[#39FF14]/40 transition-all duration-300"
            >
              <!-- Icon -->
              <div class="flex items-start gap-4 mb-4">
                <div
                  class="w-12 h-12 rounded-lg flex items-center justify-center text-2xl flex-shrink-0 transition-transform duration-300 group-hover:scale-110"
                  :style="{
                    background: item.iconBg,
                    boxShadow: `0 0 20px ${item.iconGlow}`,
                  }"
                >
                  {{ item.icon }}
                </div>
                <div class="flex-1">
                  <h4
                    class="font-display font-bold text-white text-base group-hover:text-[#39FF14] transition-colors duration-300"
                  >
                    {{ item.title }}
                  </h4>
                  <div class="font-mono text-xs text-[#39FF14]/50 mt-1">
                    {{ item.category }}
                  </div>
                </div>
              </div>

              <!-- Description -->
              <p class="text-green-100/60 text-sm leading-relaxed mb-4">
                {{ item.description }}
              </p>
            </div>
          </Motion>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Motion } from "@motionone/vue";

const skillsInterests = [
  {
    icon: "💻",
    title: "Frontend Development",
    category: "SKILL",
    description:
      "Membangun antarmuka pengguna yang responsif, interaktif, dan modern menggunakan framework terkini.",
    iconBg: "linear-gradient(135deg, #0ea5e9, #06b6d4)",
    iconGlow: "rgba(14,165,233,0.4)",
  },
  {
    icon: "⚙️",
    title: "Backend Development",
    category: "SKILL",
    description:
      "Merancang API yang efisien dan integrasi database yang optimal.",
    iconBg: "linear-gradient(135deg, #84cc16, #65a30d)",
    iconGlow: "rgba(132,204,22,0.4)",
  },
  {
    icon: "📱",
    title: "Mobile Development",
    category: "SKILL",
    description:
      "Mengembangkan aplikasi mobile pada platform Android menggunakan Java.",
    iconBg: "linear-gradient(135deg, #06b6d4, #0891b2)",
    iconGlow: "rgba(6,182,212,0.4)",
  },
  {
    icon: "💡",
    title: "Problem Solving",
    category: "SKILL",
    description:
      "Menyelesaikan masalah kompleks dengan pendekatan logis dan rasional.",
    iconBg: "linear-gradient(135deg, #ec4899, #db2777)",
    iconGlow: "rgba(236,72,153,0.4)",
  },
  {
    icon: "🤝",
    title: "Team Collaboration",
    category: "SKILL",
    description:
      "Bekerja efektif dalam tim untuk mencapai tujuan bersama dengan menjaga komunikasi yang baik dengan anggota tim.",
    iconGlow: "rgba(139,92,246,0.4)",
    iconBg: "linear-gradient(135deg, #8b5cf6, #7c3aed)",
  },
  {
    icon: "🤖",
    title: "AI & Machine Learning",
    category: "MINAT",
    description:
      "Eksplorasi teknologi AI untuk menciptakan solusi cerdas yang dapat meningkatkan user experience.",
    iconBg: "linear-gradient(135deg, #f59e0b, #d97706)",
    iconGlow: "rgba(245,158,11,0.4)",
  },
];
</script>

<style scoped>
.skill-card {
  transition: all 0.35s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.skill-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(57, 255, 20, 0.1);
}
</style>
