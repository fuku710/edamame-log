<template>
  <div>
    <HeaderTitle></HeaderTitle>
    <EdamameThumbnailList :edamames="edamames"></EdamameThumbnailList>
  </div>
</template>

<script>
import HeaderTitle from '@/components/atoms/HeaderTitle'
import EdamameThumbnailList from '@/components/organisms/EdamameThumbnailList'
export default {
  components: { HeaderTitle, EdamameThumbnailList },
  data() {
    return {
      edamames: []
    }
  },
  async mounted() {
    await this.fetchEdamames()
  },
  methods: {
    async fetchEdamames() {
      const response = await this.$axios.$get(process.env.API_URL)
      this.edamames = response.edamames.map((edamame) => ({
        imageUrl: `${process.env.S3_URL}/${edamame}`,
        date: Number(edamame.slice(0, -4)),
        month: Number(edamame.slice(2, 4)),
        day: Number(edamame.slice(4, 6))
      }))
    }
  }
}
</script>

<style>
body {
  background-color: #bbffb5;
}
</style>
