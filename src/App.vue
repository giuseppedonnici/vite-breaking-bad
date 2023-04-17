<script>
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";

export default {
  components: {
    AppHeader,
    CardList
  }

}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api"/>
  <main>
    <CardList />
  </main>

</template>

<style lang="scss">
@use "./styles/general.scss";

</style>