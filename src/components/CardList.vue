<script>
import AppCard from './AppCard.vue';
import AppLoader from './AppLoader.vue';
import CardNumber from './CardNumber.vue';
import {store} from "../store";

export default {
    name: "CardList",
    components: {
        AppCard,
        AppLoader,
        CardNumber
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
   <div class="my-container p-5">
        <AppLoader v-if="store.loading"/>
        <CardNumber />
       <!-- <h6 class="p-3">Found 39 cards</h6> -->
       <div class="row row-cols-5 g-4">
            <div class="col" v-for="card in store.cards" :key="card.id">
                <AppCard :card="card"/>

            </div>
        </div>
   </div>

</template>

<style scoped lang="scss">
    .my-container {
        background-color: white;
    }
    
</style>