<template>
  <section class="section">
    <aside class="container title">
      <h3>Nous parler</h3>
      <h2>Plus de détails ou <span>des question ?</span></h2>
    </aside>
    <form class="container">
      <fieldset>
        <transition name="slide-fade">
          <label v-show="fields.name" for="names">Votre nom & prénom*</label>
        </transition>
        <input
          id="names"
          type="text"
          name="names"
          placeholder="Votre nom & prénom*"
          @focus="fields.name = true"
        />
      </fieldset>
      <fieldset>
        <transition name="slide-fade">
          <label v-show="fields.mail" for="email">Adresse mail*</label>
        </transition>
        <input
          id="email"
          type="email"
          name="email"
          placeholder="Adresse mail*"
          @focus="fields.mail = true"
        />
      </fieldset>
      <fieldset>
        <transition name="slide-fade">
          <label v-show="fields.phone" for="tel">Téléphone</label>
        </transition>
        <input
          id="tel"
          type="tel"
          name="tel"
          placeholder="Téléphone"
          @focus="fields.phone = true"
        />
      </fieldset>
      <fieldset>
        <label for="besoins">Vous avez besoin*</label>
        <select id="besoins" name="besoins">
          <option value="D'informations">D'informations</option>
          <option value="D'un max de lol">D'un max de lol</option>
          <option value="La coke et les putes">La coke et les putes</option>
        </select>
      </fieldset>
      <fieldset>
        <label for="message">Message supplémentaire</label>
        <textarea id="message" name="message" cols="30" rows="6"></textarea>
      </fieldset>
      <input type="submit" value="Envoyer" />
    </form>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      fields: {
        name: false,
        mail: false,
        phone: false,
      },
    }
  },
}
</script>

<style scoped lang="scss" src="assets/styles/components/Contact.scss"></style>
