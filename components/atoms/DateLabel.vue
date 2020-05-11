<template>
  <div class="date-label">{{ month }}/{{ day }}</div>
</template>
<script>
export default {
  props: {
    month: { type: Number, required: true },
    day: { type: Number, required: true }
  }
}
</script>
<style scoped>
.date-label {
  font-size: 18px;
  width: 120px;
  height: 24px;
  text-align: center;
}
</style>
