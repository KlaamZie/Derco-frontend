<template>
  <section class="section">
    <div id="wrapper">
      <article>
        <h1 id="project-title">
          <span>{{ isActive.title }}</span>
        </h1>
        <aside>
          <button
            @click.prevent="handleDisplayProject"
            @mouseenter="$nuxt.$emit('hidecircle')"
            @mouseleave="$nuxt.$emit('displaycircle')"
          >
            Découvrir le projet
          </button>
        </aside>
      </article>
    </div>
    <article id="projects">
      <div
        v-for="(project, i) in projects"
        :id="project.slug"
        :key="i"
        class="project"
      >
        <img
          :src="
            'http://api.derniere-cohorte.com/assets/' +
            project.slug +
            '/slider.jpg'
          "
        />
      </div>
    </article>
  </section>
</template>

<script>
export default {
  props: {
    projects: {
      type: Array,
      default: () => {
        return []
      },
    },
  },
  data() {
    return {
      isActive: '',
      title: '',
      index: 0,
      scrollPosition: 0,
    }
  },
  mounted() {
    document.addEventListener('scroll', this.handleScroll)
    this.scrollPosition = window.scrollY
  },
  beforeDestroy() {
    document.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    async handleScroll() {
      const i = this.index
      const scroll = window.scrollY
      const project =
        document.getElementById(this.projects[i].slug).getBoundingClientRect()
          .top + scroll

      let nextProject
      if (i < this.projects.length - 1) {
        nextProject =
          document
            .getElementById(this.projects[i + 1].slug)
            .getBoundingClientRect().top + scroll
      } else {
        nextProject = null
      }

      let prevProject
      i > 0 ? (prevProject = true) : (prevProject = false)

      if (scroll >= project - 300) {
        if (this.isActive.title !== this.projects[i].title) {
          this.isActive = this.projects[i]
        }
      }

      if (this.scrollPosition - scroll < 0) {
        if (nextProject && scroll >= nextProject - 300) {
          await this.slideDown()
          this.index += 1
        }
      } else if (prevProject && scroll <= project - 150) {
        await this.slideUp()
        this.index -= 1
      }

      this.scrollPosition = window.scrollY
    },
    slideUp() {
      const title = document.getElementById('project-title')
      title.classList.add('slideUp')
      setTimeout(() => {
        title.classList.remove('slideUp')
      }, 500)
    },
    slideDown() {
      const title = document.getElementById('project-title')
      title.classList.add('slideDown')
      setTimeout(() => {
        title.classList.remove('slideDown')
      }, 500)
    },
    handleDisplayProject() {
      this.$emit('displayproject', this.isActive)
    },
  },
}
</script>

<style scoped lang="scss" src="assets/styles/components/Projects.scss"></style>
