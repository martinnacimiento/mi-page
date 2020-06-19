<template lang="pug">
  div
    v-parallax(
      :srcset="martin + ' 1080w'" 
      sizes="(max-widt: 2000px) 800px"
      :src="martin"
      height="550"
    )
      v-row(
        align="center"
        justify="center"
      )
        v-col(cols="12" class="text-center")
          .letter MN
          .subletter Estoy construyendo este sitio aun
            v-icon(color="yellow darken-2") mdi-tools
</template>

<script>
import martin from '@/assets/img/martin2.jpg'

export default {
  data: () => ({
    martin: martin
  })
}
</script>
<style scoped>

@font-face {
  font-family: 'piolon';
  src: url('~static/fonts/Noir_regular.otf') format('opentype');
}
.letter {
  font-family: 'piolon';
  font-size: 50px;
}
.subletter {
  font-family: 'piolon';
}
</style>
