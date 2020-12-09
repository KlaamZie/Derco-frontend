<template>
  <nav id="nav">
    <img src="@/assets/images/logo_web.svg" alt="" />
    <button
      id="btn-menu"
      @click="handleMenu"
      @mouseenter="$nuxt.$emit('hidecircle')"
      @mouseleave="$nuxt.$emit('displaycircle')"
    >
      <span>Menu</span>
      <span>Fermer</span>
    </button>
    <transition name="menu">
      <div v-show="displayMenu">
        <transition name="menu-first">
          <h1 v-show="displayMenu">Naviguer sur notre site</h1>
        </transition>
        <ul>
          <transition name="menu-first">
            <li v-show="displayMenu">
              <a href="#project">
                Votre Projet
                <span>
                  <svg
                    width="5"
                    height="5"
                    viewBox="0 0 5 5"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M1.25039 5H4.58338C4.69387 5 4.79984 4.95611 4.87797 4.87797C4.95611 4.79984 5 4.69387 5 4.58338V1.2504C5 1.1399 4.95611 1.03393 4.87797 0.955798C4.79984 0.877666 4.69387 0.833772 4.58338 0.833772C4.47288 0.833772 4.36691 0.877666 4.28878 0.955798C4.21065 1.03393 4.16675 1.1399 4.16675 1.2504V3.57765L0.712118 0.12218C0.633888 0.0439497 0.527784 0 0.417149 0C0.306515 0 0.200411 0.0439497 0.12218 0.12218C0.0439497 0.200411 0 0.306515 0 0.417149C0 0.527784 0.0439497 0.633888 0.12218 0.712118L3.57765 4.16675H1.25039C1.1399 4.16675 1.03393 4.21065 0.955798 4.28878C0.877666 4.36691 0.833772 4.47288 0.833772 4.58338C0.833772 4.69387 0.877666 4.79984 0.955798 4.87797C1.03393 4.95611 1.1399 5 1.25039 5Z"
                    />
                  </svg>
                  Scroll
                </span>
              </a>
            </li>
          </transition>
          <transition name="menu-second">
            <li v-show="displayMenu">
              <a href="#portfolio">
                Portfolio
                <span>
                  <svg
                    width="5"
                    height="5"
                    viewBox="0 0 5 5"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M1.25039 5H4.58338C4.69387 5 4.79984 4.95611 4.87797 4.87797C4.95611 4.79984 5 4.69387 5 4.58338V1.2504C5 1.1399 4.95611 1.03393 4.87797 0.955798C4.79984 0.877666 4.69387 0.833772 4.58338 0.833772C4.47288 0.833772 4.36691 0.877666 4.28878 0.955798C4.21065 1.03393 4.16675 1.1399 4.16675 1.2504V3.57765L0.712118 0.12218C0.633888 0.0439497 0.527784 0 0.417149 0C0.306515 0 0.200411 0.0439497 0.12218 0.12218C0.0439497 0.200411 0 0.306515 0 0.417149C0 0.527784 0.0439497 0.633888 0.12218 0.712118L3.57765 4.16675H1.25039C1.1399 4.16675 1.03393 4.21065 0.955798 4.28878C0.877666 4.36691 0.833772 4.47288 0.833772 4.58338C0.833772 4.69387 0.877666 4.79984 0.955798 4.87797C1.03393 4.95611 1.1399 5 1.25039 5Z"
                    />
                  </svg>
                  Scroll
                </span>
              </a>
            </li>
          </transition>
          <transition name="menu-third">
            <li v-show="displayMenu">
              <a href="#equipe">
                Equipe
                <span>
                  <svg
                    width="5"
                    height="5"
                    viewBox="0 0 5 5"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M1.25039 5H4.58338C4.69387 5 4.79984 4.95611 4.87797 4.87797C4.95611 4.79984 5 4.69387 5 4.58338V1.2504C5 1.1399 4.95611 1.03393 4.87797 0.955798C4.79984 0.877666 4.69387 0.833772 4.58338 0.833772C4.47288 0.833772 4.36691 0.877666 4.28878 0.955798C4.21065 1.03393 4.16675 1.1399 4.16675 1.2504V3.57765L0.712118 0.12218C0.633888 0.0439497 0.527784 0 0.417149 0C0.306515 0 0.200411 0.0439497 0.12218 0.12218C0.0439497 0.200411 0 0.306515 0 0.417149C0 0.527784 0.0439497 0.633888 0.12218 0.712118L3.57765 4.16675H1.25039C1.1399 4.16675 1.03393 4.21065 0.955798 4.28878C0.877666 4.36691 0.833772 4.47288 0.833772 4.58338C0.833772 4.69387 0.877666 4.79984 0.955798 4.87797C1.03393 4.95611 1.1399 5 1.25039 5Z"
                    />
                  </svg>
                  Scroll
                </span>
              </a>
            </li>
          </transition>
          <transition name="menu-last">
            <li v-show="displayMenu">
              <a href="#contact">
                Nous parler
                <span>
                  <svg
                    width="5"
                    height="5"
                    viewBox="0 0 5 5"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M1.25039 5H4.58338C4.69387 5 4.79984 4.95611 4.87797 4.87797C4.95611 4.79984 5 4.69387 5 4.58338V1.2504C5 1.1399 4.95611 1.03393 4.87797 0.955798C4.79984 0.877666 4.69387 0.833772 4.58338 0.833772C4.47288 0.833772 4.36691 0.877666 4.28878 0.955798C4.21065 1.03393 4.16675 1.1399 4.16675 1.2504V3.57765L0.712118 0.12218C0.633888 0.0439497 0.527784 0 0.417149 0C0.306515 0 0.200411 0.0439497 0.12218 0.12218C0.0439497 0.200411 0 0.306515 0 0.417149C0 0.527784 0.0439497 0.633888 0.12218 0.712118L3.57765 4.16675H1.25039C1.1399 4.16675 1.03393 4.21065 0.955798 4.28878C0.877666 4.36691 0.833772 4.47288 0.833772 4.58338C0.833772 4.69387 0.877666 4.79984 0.955798 4.87797C1.03393 4.95611 1.1399 5 1.25039 5Z"
                    />
                  </svg>
                  Scroll
                </span>
              </a>
            </li>
          </transition>
        </ul>
        <transition name="menu-last">
          <aside v-show="displayMenu">
            <p>contact@mail.com</p>
            <p>06 06 06 06 06</p>
          </aside>
        </transition>
      </div>
    </transition>
  </nav>
</template>

<script>
export default {
  name: 'Menu',
  data() {
    return {
      displayMenu: false,
    }
  },
  methods: {
    handleMenu() {
      const btn = document.getElementById('btn-menu')
      const span = btn.getElementsByTagName('span')
      if (this.displayMenu) {
        span[0].style.transform = 'translateY(0)'
        span[1].style.transform = 'translateY(100%)'

        if (window.innerWidth >= 1280) {
          btn.style.transform = ''
          btn.style.padding = ''
          btn.style.backgroundImage = ''
          btn.style.color = ''
          span[0].style.fontSize = ''
          span[1].style.fontSize = ''
        }
      } else {
        span[0].style.transform = 'translateY(-100%)'
        span[1].style.transform = 'translateY(0)'
        if (window.innerWidth >= 1280) {
          btn.style.transform = 'translate(60px, 40px)'
          btn.style.padding = '15px 35px'
          btn.style.backgroundImage =
            'linear-gradient(to right, #F4F4F4 50%, #89E2B7 50%)'
          btn.style.color = 'black'
          span[0].style.fontSize = '16px'
          span[1].style.fontSize = '16px'
        }
      }
      this.displayMenu = !this.displayMenu
    },
  },
}
</script>

<style scoped lang="scss" src="assets/styles/layouts/Menu.scss"></style>
