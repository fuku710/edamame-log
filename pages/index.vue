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
      console.log('API_URL', process.env.API_URL)
      console.log('IMAGE_URL', process.env.IMAGE_URL)
      const response = await this.$axios.$get(process.env.API_URL)
      this.edamames = response.edamames.map((edamame) => ({
        imageUrl: `${process.env.IMAGE_URL}/${edamame}`,
        date: Number(edamame.slice(0, -4)),
        month: Number(edamame.slice(2, 4)),
        day: Number(edamame.slice(4, 6))
      }))
    }
  }
}
</script>

<style></style>
