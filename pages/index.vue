<template>
  <main>
    <Header></Header>
    <Presentation></Presentation>
    <Tools></Tools>
    <Projects :projects="projects" @displayproject="handleDisplayProject">
    </Projects>
    <transition name="slide-fade" mode="out-in">
      <Project
        v-if="display"
        :isactive="isActive"
        @closeproject="handleCloseProject"
        @nextproject="handleNextProject"
      >
      </Project>
    </transition>
    <Team></Team>
    <Contact></Contact>
  </main>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const projects = await $content('projects').sortBy('index').fetch()
    return {
      projects,
    }
  },
  data() {
    return {
      display: false,
      isActive: {},
    }
  },
  methods: {
    handleDisplayProject(isActive) {
      this.isActive = isActive
      this.display = true
      setTimeout(() => {
        document.body.style.height = '100vh'
        document.body.style.overflow = 'hidden'
        const el = document.getElementById('displayedProject')
        el.style.overflow = 'auto'
      }, 1000)
    },
    handleCloseProject() {
      const btn = document.getElementById('closeProjectBtn')
      btn.style.opacity = '0'
      setTimeout(() => {
        const el = document.getElementById('displayedProject')
        el.style.overflow = 'hidden'
        document.body.style.height = ''
        document.body.style.overflow = 'visible'
        this.display = false
      }, 300)
      setTimeout(() => {
        btn.style.opacity = '1'
      }, 700)
    },
    handleNextProject() {
      let actual = this.projects.findIndex(
        (el) => el.slug === this.isActive.slug
      )
      if (actual < this.projects.length - 1) {
        actual += 1
      } else {
        actual = 0
      }
      this.isActive = this.projects[actual]
    },
  },
  head() {
    return {
      title: 'Dernière Cohorte - Collectif web à Montpellier',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            "Agence collaborative de freelance à Montpellier. Spécialiste en création de site internet, d'identité graphique et d'application web. - Projets uniques et création sur mesure - Devis gratuit - Délais respectés",
        },
      ],
    }
  },
}
</script>

<style scoped lang="scss">
/* Les animations d'entrée (« enter ») et de sortie (« leave »)  */
/* peuvent utiliser différentes fonctions de durée et de temps.  */
.slide-fade-enter-active {
  transition: all 1s ease;
}
.slide-fade-leave-active {
  transition: all 0.7s ease;
}
.slide-fade-enter, .slide-fade-leave-to
  /* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateY(100%);
  opacity: 0;
}
</style>
