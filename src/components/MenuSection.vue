<script setup>
const dishes = [
  { name: "春笋 · 青梅 · 鲜蚕豆", detail: "炭烤春笋，青梅汁，蚕豆泥", note: "序" },
  { name: "东海黄鱼 · 雪菜 · 酒酿", detail: "低温黄鱼，雪菜清汤，酒酿泡沫", note: "鲜" },
  { name: "茶香乳鸽 · 樱桃 · 紫苏", detail: "龙井烟熏乳鸽，樱桃酱，紫苏油", note: "香" },
  { name: "茉莉 · 枇杷 · 米酿", detail: "茉莉奶冻，枇杷冰，桂花米酿", note: "余" },
];
</script>

<template>
  <section id="menu" class="menu-section section">
    <div class="menu-intro">
      <div class="section-label light"><span>02</span> 当季菜单</div>
      <p class="kicker">Early Summer · 初夏</p>
      <h2>山野清鲜，<br>正好入席。</h2>
      <p>初夏菜单从晨露、河鲜与新绿中取味。可选择五道式或八道式品鉴菜单。</p>
      <a class="button button-outline" href="#reservation">查看完整菜单 <span>→</span></a>
    </div>
    <div class="menu-list">
      <article v-for="(dish, index) in dishes" :key="dish.name" class="dish">
        <span class="dish-no">{{ String(index + 1).padStart(2, "0") }}</span>
        <div><h3>{{ dish.name }}</h3><p>{{ dish.detail }}</p></div>
        <strong>{{ dish.note }}</strong>
      </article>
    </div>
  </section>
</template>
