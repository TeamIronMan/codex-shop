<script setup>
const dishes = [
  { name: "春笋 · 青梅 · 鲜蚕豆", detail: "炭火轻炙春笋，佐青梅清酸与新蚕豆的温润", note: "序" },
  { name: "东海黄鱼 · 雪菜 · 酒酿", detail: "低温慢煮东海黄鱼，雪菜清汤衬以酒酿幽香", note: "鲜" },
  { name: "茶香乳鸽 · 樱桃 · 紫苏", detail: "龙井烟香浸润乳鸽，樱桃微甜与紫苏清韵相和", note: "香" },
  { name: "茉莉 · 枇杷 · 米酿", detail: "茉莉奶冻轻盈柔滑，枇杷冰与桂花米酿收尾", note: "余" },
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
