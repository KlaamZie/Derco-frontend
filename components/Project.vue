<template>
  <section id="displayedProject" style="overflow: hidden">
    <button
      id="closeProjectBtn"
      @click="$emit('closeproject')"
      @mouseenter="$nuxt.$emit('hidecircle')"
      @mouseleave="$nuxt.$emit('displaycircle')"
    >
      Fermer
    </button>
    <img
      :src="
        'http://api.derniere-cohorte.com/assets/' + isactive.slug + '/1.jpg'
      "
      alt=""
      onerror="this.style.display = 'none'"
    />
    <article>
      <div>
        <h1>{{ isactive.accroche }}</h1>
        <p>{{ isactive.desc }}</p>
      </div>
      <div>
        <aside>
          <h2>Service</h2>
          <ul>
            <li v-for="(service, i) in isactive.services" :key="i">
              {{ service }}
            </li>
          </ul>
        </aside>
        <aside>
          <h2>Temps</h2>
          <p>{{ isactive.temps }}</p>
        </aside>
      </div>
    </article>
    <img
      :src="
        'http://api.derniere-cohorte.com/assets/' + isactive.slug + '/2.jpg'
      "
      alt=""
      onerror="this.style.display = 'none'"
    />
    <img
      :src="
        'http://api.derniere-cohorte.com/assets/' + isactive.slug + '/3.jpg'
      "
      alt=""
      onerror="this.style.display = 'none'"
    />
    <img
      :src="
        'http://api.derniere-cohorte.com/assets/' + isactive.slug + '/4.jpg'
      "
      alt=""
      onerror="this.style.display = 'none'"
    />
    <article>
      <button @click="handleNextProject">
        Projet Suivant
        <svg
          width="15"
          height="15"
          viewBox="0 0 15 15"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M3.64645 3.64644C3.45118 3.8417 3.45118 4.15828 3.64645 4.35354L10.2929 11L6 11C5.72386 11 5.5 11.2239 5.5 11.5C5.5 11.7761 5.72386 12 6 12L11.5 12C11.6326 12 11.7598 11.9473 11.8536 11.8536C11.9473 11.7598 12 11.6326 12 11.5L12 5.99999C12 5.72385 11.7761 5.49999 11.5 5.49999C11.2239 5.49999 11 5.72385 11 5.99999V10.2929L4.35355 3.64643C4.15829 3.45117 3.84171 3.45117 3.64645 3.64644Z"
            fill="currentColor"
            fill-rule="evenodd"
            clip-rule="evenodd"
          ></path>
        </svg>
      </button>
    </article>
  </section>
</template>

<script>
export default {
  name: 'Project',
  props: {
    isactive: {
      type: Object,
      default: () => {
        return {}
      },
    },
  },
  methods: {
    async handleNextProject() {
      const el = document.getElementById('displayedProject')
      await el.scroll({ top: 0, behavior: 'smooth' })
      this.$emit('nextproject')
    },
  },
}
</script>

<style scoped lang="scss" src="assets/styles/components/Project.scss"></style>
