<script setup>
const details = [
  { label: "品鉴菜单", value: "¥ 688 / 位起" },
  { label: "建议用餐时长", value: "约 2.5 小时" },
  { label: "私人包间", value: "2 — 10 位" },
];
</script>

<template>
  <section id="experience" class="experience section">
    <div class="experience-copy">
      <div class="section-label"><span>03</span> 用餐体验</div>
      <p class="kicker">A Quiet Table</p>
      <h2>慢一点，才尝得到<br>食物里的时间。</h2>
      <p>空间以深木、素麻与暖光营造安静的氛围。我们希望你在这里暂别匆忙，与重要的人，好好吃一顿饭。</p>
      <div class="experience-details">
        <div v-for="detail in details" :key="detail.label">
          <span>{{ detail.label }}</span><strong>{{ detail.value }}</strong>
        </div>
      </div>
    </div>
    <div class="quote-card">
      <span class="quote-mark">“</span>
      <blockquote>一道菜真正完成的时刻，不在厨房，而在客人尝到它的那一刻。</blockquote>
      <p>林叙 · 创始人兼主厨</p>
    </div>
  </section>
</template>
