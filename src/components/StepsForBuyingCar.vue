<template>
  <section>
    <li>
      <p>{{steps.stepName}}</p>
      <p>{{steps.description}}</p>
    </li>
  </section>
</template>

<script>
export default {
  name: "StepsForBuyingCar",
  props:{
    steps: Object
  }
}

</script>

<style scoped>

</style>