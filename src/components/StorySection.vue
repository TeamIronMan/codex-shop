<script setup>
const stats = [
  { value: "24", label: "节气入馔" },
  { value: "12", label: "位本地伙伴" },
  { value: "1", label: "席当季故事" },
];
</script>

<template>
  <section id="story" class="story section">
    <div class="section-label"><span>01</span> 我们的故事</div>
    <div class="story-heading">
      <p class="kicker">Seasonal · Local · Sincere</p>
      <h2>以时序为引，<br>呈一席东方雅味。</h2>
    </div>
    <div class="story-body">
      <p>叙味循四时风物而作，于山海之间甄选珍贵鲜材。我们尊重每一种食材的本真，以精准火候与细腻层次，凝练当季最纯粹的风味。</p>
      <p>主厨林叙以东方饮食美学为根基，融汇现代烹饪技艺。每一道料理皆历经悉心推敲，在克制与丰盈之间，呈现一席隽永雅致的味觉叙事。</p>
      <a class="text-link dark-link" href="#experience">了解叙味的理念 <span>→</span></a>
    </div>
    <div class="story-stats">
      <div v-for="stat in stats" :key="stat.label">
        <strong>{{ stat.value }}</strong><span>{{ stat.label }}</span>
      </div>
    </div>
  </section>
</template>
