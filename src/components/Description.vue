<template>
  <p>
    {{desc.descriptionInParagraph}}
  </p>
</template>

<script>
export default {
  name: "Description",
  props:{
    desc: Object
  }
}
</script>

<style scoped>

</style>