<template lang="pug">
  v-parallax(:src="martin")
    v-row(
      align="center"
      justify="center"
    )
      v-col(cols="12" class="text-center")
        .letter Nacimiento Martin
        .subheading Estoy construyendo este sitio aun
</template>

<script>
import martin from '@/assets/img/martin.jpg'

export default {
  data: () => ({
    martin: martin
  })
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap');
.letter {
  font-family: 'Permanent Marker', cursive;
  font-size: 50px;
  align-content: center;
  justify-content: center;
}
</style>
