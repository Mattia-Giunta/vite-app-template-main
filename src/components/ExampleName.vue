<script>
// import

export default {
  name: "ExampleName",
};
</script>

<template>
  <h1>Hi I'm component</h1>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;
@use "../styles/partials/mixins" as *;

h1 {
  color: $font-color-second;
  @include main-font-start;
}
</style>
