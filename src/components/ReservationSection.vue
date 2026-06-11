<script setup>
import { reactive } from "vue";

const emit = defineEmits(["submitted"]);
const today = new Date();
const localToday = new Date(today.getTime() - today.getTimezoneOffset() * 60000).toISOString().split("T")[0];
const initialForm = { name: "", phone: "", date: "", guests: "2 位" };
const form = reactive({ ...initialForm });

function submitReservation() {
  emit("submitted");
  Object.assign(form, initialForm);
}
</script>

<template>
  <section id="reservation" class="reservation section">
    <div class="reservation-copy">
      <p class="kicker">Reserve Your Table</p>
      <h2>留一席时间，<br>给一顿好饭。</h2>
      <p>我们每日仅接待少量客人，建议提前 3 至 7 日预订。</p>
    </div>
    <form class="reservation-form" @submit.prevent="submitReservation">
      <label>称呼<input v-model="form.name" type="text" name="name" placeholder="您的姓名" required></label>
      <label>联系电话<input v-model="form.phone" type="tel" name="phone" placeholder="手机号码" required></label>
      <label>用餐日期<input v-model="form.date" type="date" name="date" :min="localToday" required></label>
      <label>用餐人数
        <select v-model="form.guests" name="guests">
          <option v-for="guests in ['2 位', '3 位', '4 位', '5 位', '6 位及以上']" :key="guests">{{ guests }}</option>
        </select>
      </label>
      <button class="button button-primary" type="submit">提交预订申请 <span>→</span></button>
      <p class="form-note">提交后，我们将在 2 小时内与您电话确认。</p>
    </form>
  </section>
</template>
