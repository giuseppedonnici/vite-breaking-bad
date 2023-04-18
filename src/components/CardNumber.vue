<script>
import { store } from '../store';

export default {
    name:"CardNumber",
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h6 class="p-3">{{ `Found ${store.cards.length} cards` }}</h6>

</template>

<style scoped lang="scss">
    h6 {
        background-color: black;
        color: white;
    }
</style>