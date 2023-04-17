<script>
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";
import axios from "axios";
import {store} from "./store";

export default {
  components: {
    AppHeader,
    CardList
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    store.loading = true;
    axios.get(store.apiURL).then((resp) => {
      console.log(resp.data.data);
      this.store.cards = resp.data.data;
      store.loading = false;
      console.log(store.cards);
    })
  }

}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api"/>
  <main class="d-flex align-items-center p-5">
    <CardList />
  </main>

</template>

<style lang="scss">
@use "./styles/general.scss";

</style>