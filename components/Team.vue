<template>
  <section id="team" class="container section">
    <aside class="title">
      <h3>Avec qui je vais travailler ?</h3>
      <h2>
        L’équipe de la <br />
        <span>dernière cohorte</span>
      </h2>
    </aside>
    <div>
      <article>
        <img
          src="https://api.derniere-cohorte.com/assets/images/enzo_equipe.jpg"
          alt="Enzo Viry - Développeur Web - Site web - Application - Frontend - Backend - Javascript - VueJs - NuxtJs - Montpellier"
        />
        <div>
          <div>
            <h1>Enzo Viry</h1>
            <h2>Développeur Web</h2>
            <h2>Javascript / VueJs / NuxtJs</h2>
          </div>
          <p>
            L’univers du développement web a piqué ma curiosité il y a
            maintenant 10 ans. Depuis, j’ai eu la chance de travailler sur de
            nombreux projets, à la fois personnels et professionnels qui m’ont
            permis d’affiner mes compétences aussi bien techniques
            qu’organisationnelles.
          </p>
        </div>
      </article>
      <article>
        <img
          src="https://api.derniere-cohorte.com/assets/images/guillaume_equipe.jpg"
          alt="Guillaume Pinho - UX/UI Designer - Création d'identité - Branding - Création de logo - Montpellier"
        />
        <div>
          <div>
            <h1>Guillaume Pinho</h1>
            <h2>UX/UI Design</h2>
            <h2>Graphisme Print</h2>
          </div>
          <p>
            Passionné de Design graphique et spécialisé en UX/UI, de nombreux
            artistes m’inspirent au quotidien tels que Ben Bos, Saul Bass ou
            Nielsen Norman. Curieux, je suis toujours à la recherche de
            nouvelles créations graphiques pour développer mon portfolio.
          </p>
        </div>
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
