<template>
  <div>
    <Menu></Menu>
    <Nuxt />
    <Footer></Footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      App: null,
      Circle: null,
      pos: {
        x: 0,
        y: 0,
      },
    }
  },
  mounted() {
    this.init()
  },
  beforeDestroy() {
    window.removeEventListener('pointermove', (e) => {
      this.moveCircle()
    })
  },
  created() {
    this.$nuxt.$on('hidecircle', () => {
      this.hideCircle()
    })
    this.$nuxt.$on('displaycircle', () => {
      this.displayCircle()
    })
  },
  methods: {
    async init() {
      const PIXI = await import('pixi.js')
      this.App = new PIXI.Application({
        width: window.innerWidth,
        height: window.innerHeight,
        antialias: true,
        autoResize: true,
        sharedTicker: true,
        transparent: true,
      })

      document.body.appendChild(this.App.view)

      const canvas = document.getElementsByTagName('canvas')[0]
      canvas.style.position = 'fixed'
      canvas.style.top = '0'
      canvas.style.zIndex = '99'
      canvas.style.pointerEvents = 'none'

      this.Circle = new PIXI.Graphics()
      this.Circle.lineStyle(2, 0x89e2b7)
      this.Circle.drawCircle(0, 0, 25)

      this.App.stage.addChild(this.Circle)

      this.App.stage.interactive = true

      window.addEventListener('pointermove', (e) => {
        this.moveCircle(e)
      })
    },
    moveCircle(e) {
      setTimeout(() => {
        this.Circle.x = e.clientX
        this.Circle.y = e.clientY
      }, 50)
    },
    hideCircle() {
      const canvas = document.getElementsByTagName('canvas')[0]
      canvas.style.visibility = 'hidden'
    },
    displayCircle() {
      const canvas = document.getElementsByTagName('canvas')[0]
      canvas.style.visibility = 'visible'
    },
  },
}
</script>
<style scoped></style>
