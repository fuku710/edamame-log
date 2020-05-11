<template>
  <div>
    <div class="edamame-list">
      <div v-for="edamame in edamames" :key="edamame.date" class="edamame-item">
        <DateLabel :month="edamame.month" :day="edamame.day"></DateLabel>
        <Thumbnail :src="edamame.imageUrl"></Thumbnail>
      </div>
    </div>
  </div>
</template>
<script>
import DateLabel from '@/components/atoms/DateLabel'
import Thumbnail from '@/components/atoms/Thumbnail'

export default {
  components: { DateLabel, Thumbnail },
  props: {
    edamames: { type: Array, required: true }
  }
}
</script>
<style scoped>
.edamame-list {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.edamame-item {
  width: 240px;
  height: 260px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  padding: 4px;
  margin: 8px;
  box-shadow: rgba(0, 0, 0, 0.2) 2px 2px 4px 2px;
}
</style>
