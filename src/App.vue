<template>
  <div class="bg-[#050a05] text-[#e8f5e8] font-display overflow-x-hidden">
    <AppNavbar
      :scrolled="scrolled"
      :activeSection="activeSection"
      @scroll-to="scrollToSection"
    />

    <main>
      <HeroSection @scroll-to="scrollToSection" />
      <ProfilSection />
      <PortofolioSection />
      <Penugasan />
      <KontakSection />
    </main>

    <AppFooter @scroll-to="scrollToSection" />
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import AppNavbar from "./components/AppNavbar.vue";
import HeroSection from "./components/HeroSection.vue";
import ProfilSection from "./components/ProfilSection.vue";
import PortofolioSection from "./components/PortofolioSection.vue";
import KontakSection from "./components/KontakSection.vue";
import AppFooter from "./components/AppFooter.vue";
import Penugasan from "./components/Penugasan.vue";

const scrolled = ref(false);
const activeSection = ref("beranda");

const SECTIONS = ["beranda", "profil", "portofolio", "kontak"];

const handleScroll = () => {
  scrolled.value = window.scrollY > 30;

  for (let i = SECTIONS.length - 1; i >= 0; i--) {
    const el = document.getElementById(SECTIONS[i]);
    if (el && window.scrollY >= el.offsetTop - 120) {
      activeSection.value = SECTIONS[i];
      break;
    }
  }
};

const scrollToSection = (id) => {
  const el = document.getElementById(id);
  if (!el) return;
  const navbarHeight = 64;
  window.scrollTo({ top: el.offsetTop - navbarHeight, behavior: "smooth" });
  activeSection.value = id;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll, { passive: true });
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
