<template>
  <section id="kontak" class="relative py-32 overflow-hidden">
    <div class="orb w-80 h-80 bg-[#39FF14]/6 top-20 right-0" />
    <div class="orb w-60 h-60 bg-[#39FF14]/4 bottom-20 left-0" />

    <div class="max-w-5xl mx-auto px-6">
      <!-- Section header -->
      <Motion
        :initial="{ opacity: 0, y: 30 }"
        :inView="{ opacity: 1, y: 0 }"
        :transition="{ duration: 0.6 }"
      >
        <div class="text-center mb-4">
          <div class="flex items-center justify-center gap-4 mb-6">
            <span class="font-mono text-[#39FF14] text-xs tracking-widest"
              >04.</span
            >
            <h2 class="font-display text-4xl font-black text-white">
              KON<span class="neon-text">TAK</span>
            </h2>
          </div>
          <p
            class="text-green-100/50 font-mono text-sm max-w-lg mx-auto leading-relaxed"
          >
            Hubungi saya melalui media sosial berikut atau kirim email langsung.
            Saya akan merespons secepat mungkin.
          </p>
        </div>
      </Motion>

      <!-- Divider -->
      <div class="flex items-center gap-4 my-12">
        <div
          class="flex-1 h-px bg-gradient-to-r from-transparent to-[#39FF14]/30"
        />
        <span class="font-mono text-[#39FF14]/40 text-xs tracking-widest"
          >SOCIAL MEDIA</span
        >
        <div
          class="flex-1 h-px bg-gradient-to-l from-transparent to-[#39FF14]/30"
        />
      </div>

      <!-- Social Cards Grid -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-10">
        <Motion
          v-for="(social, idx) in socials"
          :key="social.name"
          :initial="{ opacity: 0, y: 40 }"
          :inView="{ opacity: 1, y: 0 }"
          :transition="{ duration: 0.5, delay: idx * 0.1 }"
        >
          <a
            :href="social.href"
            target="_blank"
            rel="noopener noreferrer"
            class="social-card glass-card rounded-xl p-6 flex flex-col items-center gap-4 group cursor-pointer"
          >
            <!-- Icon circle -->
            <div
              class="w-16 h-16 rounded-full flex items-center justify-center transition-transform duration-300 group-hover:scale-110"
              :style="{
                background: social.bg,
                boxShadow: `0 0 20px ${social.glow}`,
              }"
            >
              <component :is="social.svgIcon" />
            </div>

            <!-- Name & handle -->
            <div class="text-center">
              <div
                class="font-display font-bold text-white text-base group-hover:text-[#39FF14] transition-colors duration-300"
              >
                {{ social.name }}
              </div>
              <div class="font-mono text-xs text-green-100/50 mt-1">
                {{ social.handle }}
              </div>
            </div>

            <!-- Hover CTA -->
            <div class="h-4 overflow-hidden">
              <span
                class="font-mono text-[#39FF14] text-xs opacity-0 group-hover:opacity-100 transition-opacity duration-300 block"
              >
                ↗ Kunjungi
              </span>
            </div>
          </a>
        </Motion>
      </div>

      <!-- Email Box -->
      <Motion
        :initial="{ opacity: 0, y: 30 }"
        :inView="{ opacity: 1, y: 0 }"
        :transition="{ duration: 0.6, delay: 0.4 }"
      >
        <div
          class="glass-card rounded-xl p-8 text-center relative overflow-hidden"
        >
          <div
            class="absolute top-0 left-0 right-0 h-px bg-gradient-to-r from-transparent via-[#39FF14]/40 to-transparent"
          />
          <div
            class="absolute bottom-0 left-0 right-0 h-px bg-gradient-to-r from-transparent via-[#39FF14]/20 to-transparent"
          />

          <div class="mb-3">
            <span class="font-mono text-xs text-[#39FF14]/40 tracking-widest"
              >// DIRECT EMAIL</span
            >
          </div>

          <a
            href="mailto:email@example.com"
            class="font-display text-2xl md:text-3xl font-bold text-white hover:text-[#39FF14] transition-all duration-300 inline-flex items-center gap-3 group"
          >
            <svg
              class="w-7 h-7 text-[#39FF14] group-hover:scale-110 transition-transform duration-300 flex-shrink-0"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="1.5"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"
              />
            </svg>
            haafiz.nayyara@gmail.com
          </a>

          <p
            class="text-green-100/40 font-mono text-xs mt-4 leading-relaxed max-w-md mx-auto"
          >
            Ada pertanyaan tentang diri saya? Kirimkan email kapan saja.
          </p>

          <div class="mt-6">
            <a
              href="mailto:haafiz.nayyara@gmail.com"
              class="neon-btn inline-block font-mono text-xs tracking-widest uppercase px-8 py-3 font-bold rounded-sm"
            >
              Kirim Email Sekarang
            </a>
          </div>
        </div>
      </Motion>
    </div>
  </section>
</template>

<script setup>
import { h } from "vue";
import { Motion } from "@motionone/vue";

const GitHubIcon = () =>
  h(
    "svg",
    { viewBox: "0 0 24 24", fill: "currentColor", class: "w-8 h-8 text-white" },
    [
      h("path", {
        d: "M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z",
      }),
    ],
  );

const InstagramIcon = () =>
  h(
    "svg",
    { viewBox: "0 0 24 24", fill: "currentColor", class: "w-8 h-8 text-white" },
    [
      h("path", {
        d: "M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z",
      }),
    ],
  );

const WhatsAppIcon = () =>
  h(
    "svg",
    { viewBox: "0 0 24 24", fill: "currentColor", class: "w-8 h-8 text-white" },
    [
      h("path", {
        d: "M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z",
      }),
    ],
  );

const LinkedInIcon = () =>
  h(
    "svg",
    { viewBox: "0 0 24 24", fill: "currentColor", class: "w-8 h-8 text-white" },
    [
      h("path", {
        d: "M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z",
      }),
    ],
  );

const socials = [
  {
    name: "GitHub",
    handle: "@haafiznayyara",
    href: "https://github.com/haafiznayyara",
    bg: "linear-gradient(135deg, #1a1a1a, #333)",
    glow: "rgba(255,255,255,0.15)",
    svgIcon: GitHubIcon,
  },
  {
    name: "Instagram",
    handle: "@haafiznayyara_09",
    href: "https://instagram.com/haafiznayyara_09",
    bg: "linear-gradient(135deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888)",
    glow: "rgba(220,39,67,0.4)",
    svgIcon: InstagramIcon,
  },
  {
    name: "WhatsApp",
    handle: "+62 8212-0073-802",
    href: "https://wa.me/6282120073802",
    bg: "linear-gradient(135deg, #25d366, #128c7e)",
    glow: "rgba(37,211,102,0.4)",
    svgIcon: WhatsAppIcon,
  },
  {
    name: "LinkedIn",
    handle: "@Mohammad Haafiz",
    href: "https://linkedin.com/in/mohammad-haafiz-mawla-nayyara-926481372",
    bg: "linear-gradient(135deg, #0077b5, #005885)",
    glow: "rgba(0,119,181,0.4)",
    svgIcon: LinkedInIcon,
  },
];
</script>

<style scoped>
.social-card {
  transition: all 0.35s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.social-card:hover {
  transform: translateY(-10px);
  border-color: rgba(57, 255, 20, 0.4);
  box-shadow:
    0 20px 40px rgba(57, 255, 20, 0.12),
    0 0 0 1px rgba(57, 255, 20, 0.1);
}
</style>
