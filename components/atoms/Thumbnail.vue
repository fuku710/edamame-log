<template>
  <div class="thumbnail-container">
    <img class="thumbnail" :src="src" />
  </div>
</template>
<script>
export default {
  props: {
    src: { type: String, required: true }
  },
  computed: {
    backgroundImageStyle() {
      return { backgeoundImage: this.imageUrl }
    }
  }
}
</script>
<style scoped>
.thumbnail-container {
  width: 240px;
  height: 240px;
  display: flex;
  align-items: center;
}
.thumbnail {
  width: 100%;
}
</style>
