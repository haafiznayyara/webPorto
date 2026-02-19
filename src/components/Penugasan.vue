<template>
  <section id="tugas" class="relative py-32 overflow-hidden bg-[#0c160c]/30">
    <div class="orb w-80 h-80 bg-[#39FF14]/5 top-0 left-1/2 -translate-x-1/2" />
    <div class="orb w-64 h-64 bg-[#39FF14]/4 bottom-0 right-0" />

    <div class="max-w-6xl mx-auto px-6">
      <!-- Section header -->
      <Motion
        :initial="{ opacity: 0, y: 30 }"
        :inView="{ opacity: 1, y: 0 }"
        :transition="{ duration: 0.6 }"
      >
        <div class="flex items-center gap-4 mb-4">
          <span class="font-mono text-[#39FF14] text-xs tracking-widest"
            >05.</span
          >
          <h2 class="font-display text-4xl font-black text-white">
            TUGAS <span class="neon-text">SAYA</span>
          </h2>
          <div
            class="flex-1 h-px bg-gradient-to-r from-[#39FF14]/30 to-transparent"
          />
        </div>
        <p class="text-green-100/50 font-mono text-sm mb-12 ml-12">
          Berikut adalah koleksi tugas dan project yang telah saya kerjakan
        </p>
      </Motion>

      <!-- Tasks Grid -->
      <div class="space-y-8">
        <!-- TUGAS 1: Document with Button -->
        <Motion
          :initial="{ opacity: 0, y: 40 }"
          :inView="{ opacity: 1, y: 0 }"
          :transition="{ duration: 0.6, delay: 0.1 }"
        >
          <div
            class="glass-card rounded-xl overflow-hidden border border-[#39FF14]/10 hover:border-[#39FF14]/30 transition-all duration-300"
          >
            <div class="p-6 md:p-8">
              <div
                class="flex flex-col md:flex-row md:items-center md:justify-between gap-4"
              >
                <!-- Left: Title & Description -->
                <div class="flex-1">
                  <div class="flex items-center gap-3 mb-3">
                    <div
                      class="w-10 h-10 rounded-lg bg-gradient-to-br from-blue-500 to-cyan-500 flex items-center justify-center text-white text-xl shadow-lg shadow-blue-500/30"
                    >
                      📄
                    </div>
                    <div>
                      <h3 class="font-display text-xl font-bold text-white">
                        Tugas 1: Laporan Penelitian
                      </h3>
                      <div
                        class="font-mono text-xs text-[#39FF14]/50 tracking-wider"
                      >
                        DOCUMENT
                      </div>
                    </div>
                  </div>
                  <p
                    class="text-green-100/60 text-sm leading-relaxed mb-4 md:mb-0"
                  >
                    Laporan lengkap tentang analisis sistem dan rekomendasi
                    implementasi teknologi terbaru untuk meningkatkan efisiensi
                    proses bisnis.
                  </p>
                </div>

                <!-- Right: Button -->
                <div class="flex items-center gap-3">
                  <a
                    href="https://5c97a56f.portfolio-vue-77d.pages.dev/"
                    target="_blank"
                    class="neon-btn font-mono text-xs tracking-widest uppercase px-6 py-3 rounded-sm font-bold flex items-center gap-2 whitespace-nowrap"
                  >
                    <svg
                      class="w-4 h-4"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
                      />
                    </svg>
                    Buka Dokumen
                  </a>
                </div>
              </div>
            </div>
          </div>
        </Motion>

        <!-- TUGAS 2: Poster PDF Preview -->
        <Motion
          :initial="{ opacity: 0, y: 40 }"
          :inView="{ opacity: 1, y: 0 }"
          :transition="{ duration: 0.6, delay: 0.2 }"
        >
          <div
            class="glass-card rounded-xl overflow-hidden border border-[#39FF14]/10 hover:border-[#39FF14]/30 transition-all duration-300"
          >
            <div class="p-6 md:p-8">
              <!-- Header -->
              <div
                class="flex flex-col md:flex-row md:items-center md:justify-between gap-4 mb-8"
              >
                <!-- Left: Title & Description -->
                <div class="flex-1">
                  <div class="flex items-center gap-3 mb-3">
                    <div
                      class="w-10 h-10 rounded-lg bg-gradient-to-br from-blue-500 to-cyan-500 flex items-center justify-center text-white text-xl shadow-lg shadow-blue-500/30"
                    >
                      📄
                    </div>
                    <div>
                      <h3 class="font-display text-xl font-bold text-white">
                        Tugas 1: Laporan Penelitian
                      </h3>
                      <div
                        class="font-mono text-xs text-[#39FF14]/50 tracking-wider"
                      >
                        DOCUMENT
                      </div>
                    </div>
                  </div>
                  <p
                    class="text-green-100/60 text-sm leading-relaxed mb-4 md:mb-0"
                  >
                    Laporan lengkap tentang analisis sistem dan rekomendasi
                    implementasi teknologi terbaru untuk meningkatkan efisiensi
                    proses bisnis.
                  </p>
                </div>

                <!-- Right: Button -->
                <div class="flex items-center gap-3">
                  <a
                    href="https://drive.google.com/file/d/12ZLK7gagDn0F6oWuGsSehpqOKNLJCfpE/view?usp=drive_link"
                    target="_blank"
                    class="neon-btn font-mono text-xs tracking-widest uppercase px-6 py-3 rounded-sm font-bold flex items-center gap-2 whitespace-nowrap"
                  >
                    Detail
                  </a>
                </div>
              </div>
            </div>
          </div>
        </Motion>

        <!-- TUGAS 3: Video Player -->
        <Motion
          :initial="{ opacity: 0, y: 40 }"
          :inView="{ opacity: 1, y: 0 }"
          :transition="{ duration: 0.6, delay: 0.3 }"
        >
          <div
            class="glass-card rounded-xl overflow-hidden border border-[#39FF14]/10 hover:border-[#39FF14]/30 transition-all duration-300"
          >
            <div class="p-6 md:p-8">
              <!-- Header -->
              <div class="flex items-center gap-3 mb-6">
                <div
                  class="w-10 h-10 rounded-lg bg-gradient-to-br from-purple-500 to-indigo-500 flex items-center justify-center text-white text-xl shadow-lg shadow-purple-500/30"
                >
                  🎬
                </div>
                <div>
                  <h3 class="font-display text-xl font-bold text-white">
                    Tugas 3: Video Presentasi Project
                  </h3>
                  <div
                    class="font-mono text-xs text-[#39FF14]/50 tracking-wider"
                  >
                    VIDEO CONTENT
                  </div>
                </div>
              </div>

              <p class="text-green-100/60 text-sm leading-relaxed mb-6">
                Video presentasi yang menjelaskan konsep, implementasi, dan
                hasil dari project aplikasi mobile yang telah dikembangkan
                menggunakan metodologi Agile.
              </p>

              <!-- Video Player -->
              <div
                class="relative rounded-lg overflow-hidden border-2 border-[#39FF14]/20 hover:border-[#39FF14]/40 transition-all duration-300 shadow-xl shadow-black/50 group"
              >
                <!-- <video
                  ref="videoPlayer"
                  class="w-full aspect-video bg-black"
                  controls
                  preload="metadata"
                  @click="togglePlay"
                >
                  <source
                    src="https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"
                    type="video/mp4"
                  />
                  <source
                    src="https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4"
                    type="video/webm"
                  />
                  Browser Anda tidak mendukung video player.
                </video> -->
              </div>
            </div>
          </div>
        </Motion>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { Motion } from "@motionone/vue";

const videoPlayer = ref(null);
const isPlaying = ref(false);

const togglePlay = () => {
  if (!videoPlayer.value) return;

  if (videoPlayer.value.paused) {
    videoPlayer.value.play();
    isPlaying.value = true;
  } else {
    videoPlayer.value.pause();
    isPlaying.value = false;
  }
};

// Listen to video events
if (typeof window !== "undefined") {
  setTimeout(() => {
    if (videoPlayer.value) {
      videoPlayer.value.addEventListener("play", () => {
        isPlaying.value = true;
      });
      videoPlayer.value.addEventListener("pause", () => {
        isPlaying.value = false;
      });
      videoPlayer.value.addEventListener("ended", () => {
        isPlaying.value = false;
      });
    }
  }, 100);
}
</script>

<style scoped>
/* Custom video controls styling (optional) */
video::-webkit-media-controls-panel {
  background-image: linear-gradient(
    to bottom,
    rgba(5, 10, 5, 0.8),
    rgba(5, 10, 5, 0.95)
  );
}

video::-webkit-media-controls-play-button,
video::-webkit-media-controls-current-time-display,
video::-webkit-media-controls-time-remaining-display {
  color: #39ff14;
}

video::-webkit-media-controls-timeline {
  background-color: rgba(57, 255, 20, 0.2);
}
</style>
