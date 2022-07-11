<template>
<section class="text-start">
  <h1><strong>{{ descForLegalEntities.heading1 }}</strong></h1>
  <p>{{ descForLegalEntities.paragraph1 }}</p>
  <ul>
    <li v-html="descForLegalEntities.li1"></li>
    <li>{{ descForLegalEntities.li2 }}</li>
    <li>{{ descForLegalEntities.li3 }}</li>
    <li>{{ descForLegalEntities.li4 }}</li>
    <li>{{ descForLegalEntities.li5 }}</li>
    <li v-html="descForLegalEntities.li6"></li>
    <li v-html="descForLegalEntities.li7"></li>
  </ul>
  <p>{{ descForLegalEntities.paragraph2 }}</p>
  <div v-html="descForLegalEntities.paragraph3"></div>
  <hr>
</section>
</template>
<script>
export default {
  name: "DocumentationForLegalEntities",
  props: {
    descForLegalEntities: Object
  }
}
</script>

<style scoped>

</style>