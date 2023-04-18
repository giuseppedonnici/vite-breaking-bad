<script>
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";
import AppSelect from "./components/AppSelect.vue";
import axios from "axios";
import {store} from "./store";

export default {
  components: {
    AppHeader,
    CardList,
    AppSelect
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    store.loading = true;
    axios.get(this.store.apiURL, {
      params: {
        num: 20,
        offset: 0
      }
    }).then((resp) => {
      this.store.cards = resp.data.data;
      store.loading = false;
    })
  },
  methods: {
    handleFilter() {
      console.log("funziona");
      store.loading = true;
      const params = {};
      if(this.store.selectedArchetype) {
        params.archetype = this.store.selectedArchetype;
      }

      axios.get(this.store.apiURL, {
        params
      }).then(resp => {
        this.store.cards = resp.data.data;
      }).catch(error => {
        console.log(error);
      }).finally(() => {
        this.store.loading = false;
      })

    }     
  }

}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api"/>
  <main class="d-flex flex-column align-items-center p-5 g-4">
    <AppSelect @filter="hadleFilter" />
    <CardList />
  </main>

</template>

<style lang="scss">
@use "./styles/general.scss";

</style>