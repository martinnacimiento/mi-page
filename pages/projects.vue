<template lang="pug">
  v-row
    v-col(v-if="$fetchState.pending" v-for="index in 10" :key="index" cols="12" sm="12" md="4")
      v-skeleton-loader(
        class="mx-auto rounded-lg"
        max-width="344"
        type="card, list-item-two-line, actions"
        :elevation="12"
      )
    v-col(v-for="p in projects" :key="p.name" cols="12" sm="12" md="4")
      v-card(
        class="rounded-lg mx-auto"
        max-width="344"
        :elevation="12"
      )
        v-img(v-if="p.image" :src="p.image" height="300px")
          template(#placeholder)
            v-row(class="fill-height ma-0" align="center" justify="center")
              v-progress-circular(indeterminate color="black lighten-5")
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
  async fetch() {
    const snap = await this.$fireStore.collection('projects').get()
    this.projects = await snap.docs.map((p) => p.data())
  },
  data: () => ({
    projects: []
  }),
  methods: {
    href(url) {
      window.open(url, '__blank')
    }
  }
}
</script>
