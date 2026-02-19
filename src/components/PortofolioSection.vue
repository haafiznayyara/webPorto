<template>
  <section id="portofolio" class="relative py-32 overflow-hidden">
    <div class="orb w-96 h-96 bg-[#39FF14]/5 top-20 -left-48" />

    <div class="max-w-6xl mx-auto px-6">
      <!-- Section header -->
      <Motion
        :initial="{ opacity: 0, y: 30 }"
        :inView="{ opacity: 1, y: 0 }"
        :transition="{ duration: 0.6 }"
      >
        <div class="flex items-center gap-4 mb-14">
          <span class="font-mono text-[#39FF14] text-xs tracking-widest"
            >03.</span
          >
          <h2 class="font-display text-4xl font-black text-white">
            PORTO<span class="neon-text">FOLIO</span>
          </h2>
          <div
            class="flex-1 h-px bg-gradient-to-r from-[#39FF14]/30 to-transparent"
          />
        </div>
      </Motion>

      <!-- Cards grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <Motion
          v-for="(project, idx) in filteredProjects"
          :key="project.id"
          :initial="{ opacity: 0, y: 40 }"
          :inView="{ opacity: 1, y: 0 }"
          :transition="{ duration: 0.5, delay: idx * 0.08 }"
        >
          <div
            class="glass-card portfolio-card rounded-lg overflow-hidden group cursor-pointer h-full"
          >
            <!-- Image area -->
            <div
              class="h-44 relative overflow-hidden"
              :style="{ background: project.bg }"
            >
              <div
                class="absolute inset-0 bg-[#050a05]/40 group-hover:bg-[#050a05]/20 transition-all duration-300"
              />
              <!-- Grid overlay -->
              <div
                class="absolute inset-0 opacity-20"
                style="
                  background-image:
                    linear-gradient(
                      rgba(57, 255, 20, 0.3) 1px,
                      transparent 1px
                    ),
                    linear-gradient(
                      90deg,
                      rgba(57, 255, 20, 0.3) 1px,
                      transparent 1px
                    );
                  background-size: 20px 20px;
                "
              />
              <!-- Category badge -->
              <div class="absolute top-3 left-3 z-10">
                <span
                  class="font-mono text-xs px-2 py-1 bg-[#050a05]/70 border border-[#39FF14]/30 text-[#39FF14] rounded-sm opacity-100 group-hover:opacity-0 transition-opacity duration-300"
                >
                  {{ project.category }}
                </span>
              </div>

              <!-- Hover overlay -->
              <div
                class="absolute inset-0 flex items-center justify-center opacity-50 group-hover:opacity-100 transition-all duration-300 p-10 group-hover:p-8"
              >
                <img :src="project.image" :alt="project.title" />
              </div>
              <div class="absolute bottom-3 right-3 text-3xl">
                {{ project.icon }}
              </div>
            </div>

            <!-- Content -->
            <div class="p-5">
              <h3 class="font-display font-bold text-white text-lg mb-2">
                {{ project.title }}
              </h3>
              <p class="text-green-100/50 text-xs leading-relaxed mb-4">
                {{ project.description }}
              </p>
              <div class="flex flex-wrap gap-1.5">
                <span
                  v-for="tag in project.tags"
                  :key="tag"
                  class="font-mono text-xs px-2 py-0.5 bg-[#39FF14]/10 text-[#39FF14]/70 rounded-sm"
                >
                  {{ tag }}
                </span>
              </div>
            </div>
          </div>
        </Motion>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";
import { Motion } from "@motionone/vue";

import billing from "../assets/porto/billing.png";
import emet from "../assets/porto/emet.png";
import rekamMedis from "../assets/porto/rekamMedis.png";
import pelaporanPekerjaan from "../assets/porto/pelaporanPekerjaan.png";
import movieMeter from "../assets/porto/movieMeter.png";
import simPel from "../assets/porto/simPel.png";
import rpl from "../assets/porto/rpl.png";

const activeFilter = ref("Semua");

const projects = [
  {
    id: 1,
    title: "Pagii Billing",
    description:
      "Sistem penagihan digital untuk bisnis kecil dengan fitur otomatisasi, laporan keuangan, dan integrasi pembayaran online.",
    category: "Bug Fixer",
    tags: ["PHP", "Bootsrap", "MySQL", "Mailtrap", "Git", "Ngrok"],
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #0a0c1a, #0f152d, #080a16)",
    image: billing,
  },
  {
    id: 2,
    title: "Pagii e-Meterai",
    description:
      "Platform digital untuk pembelian dan manajemen meterai elektronik dengan integrasi API pemerintah dan Notifikasi real-time.",
    category: "Frontend Dev",
    tags: [
      "React JS",
      "Express JS",
      "PostgreSQL",
      "Tailwind",
      "Captcha",
      "JWT",
      "oAuth",
      "Mailtrap",
    ],
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #0c1a0c, #0f2d0f, #0a160a)",
    image: emet,
  },
  {
    id: 3,
    title: "Sehat Indonesiaku",
    description:
      "Aplikasi berbasis web untuk manajemen rekam medis pasien dengan fitur jadwal dan laporan kesehatan.",
    category: "Fullstack Dev",
    tags: ["PHP", "Laravel", "MySQL", "Tailwind"],
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #1a0c0c, #2d0f0f, #160a0a)",
    image: rekamMedis,
  },
  {
    id: 4,
    title: "Aplikasi Pelaporan Pekerjaan",
    description:
      "Aplikasi berbasis web untuk pelaporan dan manajemen pekerjaan dengan fitur dashboard, monitoring pekerjaan, dan laporan kinerja.",
    category: "Fullstack Dev",
    tags: ["Next JS", "MySQL", "Tailwind"],
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #0c1a18, #0f2d28, #0a1614)",
    image: pelaporanPekerjaan,
  },
  {
    id: 5,
    title: "Internet Movie Meter",
    description:
      "Platform rekomendasi film berdasarkan rating pengguna dengan fitur pencarian, ulasan, trailer dan filtering.",
    category: "Fullstack Dev",
    tags: ["Laravel", "Bootstrap", "MySQL"],
    image: movieMeter,
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #1a0c1a, #2d0f2d, #160a16)",
  },
  {
    id: 6,
    title: "SimPel App",
    description:
      "Design landing page aplikasi SimPel App dengan tampilan modern dan responsif.",
    category: "Frontend Dev",
    tags: ["HTML", "Tailwind CSS"],
    image: simPel,
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #1a1a0c, #2d2d0f, #16160a)",
  },
  {
    id: 7,
    title: "Ketua Divisi",
    description:
      "Ketua Divisi Olahraga juruan Rekayasa Perangkat Lunak SMK Negeri 1 Cimahi Angkatan 49.",
    category: "Organisasi",
    // tags: ["HTML", "Tailwind CSS"],
    image: rpl,
    demo: "#",
    github: "#",
    bg: "linear-gradient(135deg, #1a1a0c, #2d2d0f, #16160a)",
  },
];

const filteredProjects = computed(() =>
  activeFilter.value === "Semua"
    ? projects
    : projects.filter((p) => p.category === activeFilter.value),
);
</script>
