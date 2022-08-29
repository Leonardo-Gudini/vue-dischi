<template>
  <header class="d-flex justify-content-between align-items-center px-3">
    <div class="logo-container">
        <img class="logo" src="../assets/logo.png" alt="logo">
    </div>

    <div class="search">
      <select class="form-select" aria-label="Default select example">
        <option selected>Seleziona genere</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
    name: "MyHeader.vue",
}

</script>

<style lang="scss">
    @import "../style/headerStyle.scss";
</style>