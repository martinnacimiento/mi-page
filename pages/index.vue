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
      v-row(
        align="end"
        justify="center"
      )
        v-col(cols="12" class="text-center")
          v-btn(fab small @click="href('https://github.com/martinnacimiento')").mr-2
            v-icon mdi-github
          v-btn(fab small @click="href('https://www.linkedin.com/in/martinnacimiento/')").mr-2
            v-icon mdi-linkedin
          v-btn(fab small @click="href('https://dev.to/martinnacimiento')").mr-2
            v-icon mdi-dev-to
</template>

<script>
import Martin from '@/assets/img/martin.jpg'

export default {
  data: () => ({
    martin: Martin
  }),
  methods: {
    href(url) {
      window.open(url, '_black')
    }
  }
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
