<template lang="pug">
  v-app(dark)
    v-navigation-drawer(v-model='drawer' :mini-variant='miniVariant' :clipped='clipped' fixed app)
      v-list
        v-list-item(v-for='(item, i) in items' :key='i' :to='item.to' router exact)
          v-list-item-action
            v-icon {{ item.icon }}
          v-list-item-content
            v-list-item-title(v-text='item.title')
              
              
    v-app-bar(app color="transparent" flat absolute)
      v-btn(fab small @click.stop='drawer = !drawer').mr-2
        v-icon mdi-dots-vertical

      v-toolbar-title(v-text='title').letter

      v-spacer
      v-tooltip(bottom)
        template(#activator="{on}")
          v-btn(fab small @click='modeDark = !modeDark' v-on="on").mr-2
            v-icon mdi-theme-light-dark
        span Modo noche
    v-main
      v-container(fluid)
        nuxt
          
    v-footer(:fixed='fixed' app)
      span.subletter Nacimiento Martin © {{ new Date().getFullYear() }}
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      modeDark: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Bienvenido',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Proyectos',
          to: '/projects'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Nacimiento Martin'
    }
  },
  watch: {
    modeDark(value) {
      this.$vuetify.theme.dark = value
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
  font-size: 25px;
}
.subletter {
  font-family: 'piolon';
}
</style>