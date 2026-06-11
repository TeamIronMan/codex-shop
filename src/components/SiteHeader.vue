<script setup>
import { ref } from "vue";
import BrandLogo from "./BrandLogo.vue";

const menuOpen = ref(false);
const links = [
  { href: "#story", label: "关于我们" },
  { href: "#menu", label: "当季菜单" },
  { href: "#experience", label: "用餐体验" },
  { href: "#reservation", label: "预订餐位", cta: true },
];
</script>

<template>
  <header class="site-header">
    <BrandLogo />
    <button
      class="menu-toggle"
      type="button"
      aria-label="打开菜单"
      :aria-expanded="menuOpen"
      aria-controls="main-navigation"
      @click="menuOpen = !menuOpen"
    >
      <span></span><span></span>
    </button>
    <nav id="main-navigation" class="nav-links" :class="{ open: menuOpen }" aria-label="主导航">
      <a
        v-for="link in links"
        :key="link.href"
        :href="link.href"
        :class="{ 'nav-cta': link.cta }"
        @click="menuOpen = false"
      >
        {{ link.label }}
      </a>
    </nav>
  </header>
</template>
