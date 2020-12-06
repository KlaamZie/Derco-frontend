<template>
  <section class="container section">
    <aside class="title">
      <h3>Notre équipe</h3>
      <h2>
        L’équipe de la <br />
        <span>dernière cohorte</span>
      </h2>
    </aside>
    <div>
      <article>
        <img src="@/assets/images/moi.png" alt="test" />
        <h1>Enzo Viry</h1>
        <h2>Développeur Web</h2>
        <h2>Javascript / VueJs / NuxtJs</h2>
      </article>
      <article>
        <img src="@/assets/images/moi.png" alt="test" />
        <h1>Guillaume Pinho</h1>
        <h2>UX/UI Designer</h2>
        <h2>Graphiste Print</h2>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Team',
}
</script>

<style scoped lang="scss" src="assets/styles/components/Team.scss"></style>
