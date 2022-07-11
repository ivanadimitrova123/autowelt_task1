<template>
  <section class="text-start">
    <div v-html="descForNaturalPerson.heading1"></div>
    <div v-html="descForNaturalPerson.paragraph1"></div>
    <ul>
      <li>{{ descForNaturalPerson.li1 }}</li>
      <li v-html="descForNaturalPerson.li2"></li>
      <li> {{ descForNaturalPerson.li3 }}</li>
      <li> {{ descForNaturalPerson.li4 }}</li>
      <li v-html="descForNaturalPerson.li5"></li>
      <li v-html="descForNaturalPerson.li6"></li>
      <li>{{ descForNaturalPerson.li7 }}</li>
      <li>{{ descForNaturalPerson.li8 }}</li>
      <li v-html="descForNaturalPerson.li9"></li>
    </ul>
    <div v-html="descForNaturalPerson.paragraph2"></div>
    <div v-html="descForNaturalPerson.paragraph3"></div>
    <hr>
  </section>
</template>

<script>
export default {
  name: "DocumentationForNaturalPerson",
  props: {
    descForNaturalPerson: Object
  }
}
</script>

<style scoped>

</style>