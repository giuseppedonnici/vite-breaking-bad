<script>
export default {
    name: "AppHeader",
    props: {
        title: String
    }
}
</script>

<template>
    <header>
        <img class="m-4" src="../assets/img/logo.png" alt="">
        <h1 class="container">{{ title }}</h1>
    </header>
</template>

<style scoped lang="scss">
    header {
        line-height: 80px;
        background-color: white;
        color:black;
        img {
            width: 50px;
        }
        h1 {
            display: inline-block;
            vertical-align: middle;
        }
    }
</style>