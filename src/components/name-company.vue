<template>
  <h1>{{name}}</h1>
</template>

<script>
export default {
  name: "name-company",
  props:[
      "name"
  ]
}
</script>

<style scoped>
h1{
  background-color: red;
}
</style>