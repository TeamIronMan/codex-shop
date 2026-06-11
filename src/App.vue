<script setup>
import { ref } from "vue";
import SiteHeader from "./components/SiteHeader.vue";
import HeroSection from "./components/HeroSection.vue";
import StorySection from "./components/StorySection.vue";
import MenuSection from "./components/MenuSection.vue";
import ExperienceSection from "./components/ExperienceSection.vue";
import ReservationSection from "./components/ReservationSection.vue";
import SiteFooter from "./components/SiteFooter.vue";

const toastVisible = ref(false);
let toastTimer;

function showToast() {
  toastVisible.value = true;
  window.clearTimeout(toastTimer);
  toastTimer = window.setTimeout(() => {
    toastVisible.value = false;
  }, 3600);
}
</script>

<template>
  <SiteHeader />
  <main>
    <HeroSection />
    <StorySection />
    <MenuSection />
    <ExperienceSection />
    <ReservationSection @submitted="showToast" />
  </main>
  <SiteFooter />
  <div class="toast" :class="{ show: toastVisible }" role="status" aria-live="polite">
    预约申请已收到，我们会尽快联系您。
  </div>
</template>
