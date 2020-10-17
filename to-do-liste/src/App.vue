<template>
  <div id="app">
  <contenu></contenu>
    <header-top></header-top>
  </div>
</template>

<script>

  import Contenu from "./components/Contenu";
  import header from "./components/header";

export default {
  name: 'App',
  components: {
    'contenu':Contenu,
    'header-top':header
  }
}
</script>

<style>

</style>
