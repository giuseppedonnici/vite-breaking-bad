<script>
export default {
    name: "AppCard",
    props: {
        card: Object
    }
}
</script>

<template>
    <div class="my-card text-center">
        <img :src="card.card_images[0].image_url_small" alt="">
        <h5 class="p-2">{{card.name}}</h5>
        <p>{{ card.archetype }}</p>
    </div>
</template>

<style scoped lang="scss">
    .my-card {
        height: 370px;
        background-color: orange;
        h5 {
            color: white;
        }
    }
</style>