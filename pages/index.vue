<template lang="pug">
  v-parallax(:src="martin")
    v-row(
      align="center"
      justify="center"
    )
      v-col(cols="12" class="text-center")
        .letter Nacimiento Martin
        .subheading Estoy construyendo este sitio aun
          v-icon(color="yellow darken-2") mdi-tools
</template>

<script>
import martin from '@/assets/img/martin.jpg'

export default {
  head () {
    return {
      link: [
        { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap' }
      ]
    }
  },
  data: () => ({
    martin: martin
  })
}
</script>
<style scoped>
.letter {
  font-family: 'Permanent Marker', cursive;
  font-size: 50px;
  align-content: center;
  justify-content: center;
}
</style>
