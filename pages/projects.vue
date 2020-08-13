<template lang="pug">
  v-row
    v-col(v-for="p in projects" :key="p.name" cols="12" sm="12" md="4")
      v-card(
        class="rounded-lg"
        max-width="344"
        :elevation="12"
      )
        v-img(v-if="p.image" :src="p.image" height="300px")
        v-card-title {{ p.name }}
        v-card-subtitle {{ p.status }}
        v-card-actions
          v-btn(text @click="href(p.link)") Github
            v-icon.ml-2 mdi-github
          v-btn(text @click="href(p.url)") Probar
            v-icon.ml-2 mdi-rocket
          <v-spacer></v-spacer>

          v-btn(icon @click='p.show = !p.show')
            v-icon {{ p.show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}
        v-expand-transition
          div(v-show='p.show')
            v-divider
            v-card-text {{ p.description }}
</template>
<script>
export default {
  name: 'projects',
  data: () => ({
    projects: [
      {
        name: 'CV',
        image:
          'https://dev-to-uploads.s3.amazonaws.com/i/5n60lff4i7t4cuv29yxn.png',
        description: 'Es mi curriculum vitae hecho con Vue y Vuetify',
        link: 'https://github.com/martinnacimiento/cv',
        url: 'https://martinnacimiento.github.io/cv/',
        status: 'En producción',
        show: false
      },
      {
        name: 'Crypto Exchange',
        image:
          'https://dev-to-uploads.s3.amazonaws.com/i/1jj6yt53xc8zav8uwhsb.png',
        description:
          'Proyecto para obtener las cotizaciones de las cryptomonedas mas importantes a través de la API REST de Coincap.',
        link: 'https://github.com/martinnacimiento/platzi-exchange',
        url: 'https://cryptoxchange.netlify.com/',
        status: 'En producción',
        show: false
      },
      {
        name: 'Octolion Ecommerce',
        image:
          'https://dev-to-uploads.s3.amazonaws.com/i/c1naohq32qqx32qe9sv1.png',
        description:
          'Proyecto ecommerce para visualizar y ver detalles de productos, con CRUD a través de API RESTful.',
        link: 'https://github.com/martinnacimiento/api-restful-express.js',
        url: 'https://octolion.martinnacimiento98.now.sh/',
        status: 'En producción',
        show: false
      },
      {
        name: 'Mi anterior web',
        image:
          'https://dev-to-uploads.s3.amazonaws.com/i/nh25g914n21kxmwa6pp4.png',
        description:
          'Esta fue mi primer web implementada con Bulma CSS y VueJs.',
        link: 'https://github.com/martinnacimiento/about-me',
        url: 'https://martinnacimiento.github.io/',
        status: 'En producción',
        show: false
      }
    ]
  }),
  methods: {
    href(url) {
      window.open(url, '__blank')
    }
  }
}
</script>
