<script>
export default {
    name: "AppLoader"
}
</script>

<template>
    <div class="loading-container d-flex flex-column align-items-center">
        <h3 class="text-center">Loading...</h3>
        <div class="hypnotic m-5">
        </div>
    </div>
</template>

<style scoped lang="scss">

.hypnotic {
   width: 67.2px;
   height: 28px;
   border: 2.2px solid #474bff;
   border-radius: 50%;
   display: grid;
   animation: hypnotic-ds34hk 2s infinite linear;
}

.hypnotic:before,
.hypnotic:after {
   content: "";
   grid-area: 1/1;
   border: inherit;
   border-radius: 50%;
   animation: inherit;
   animation-duration: 3s;
}

.hypnotic:after {
   --s: -1;
}

@keyframes hypnotic-ds34hk {
   100% {
      transform: rotate(calc(var(--s,1)*1turn));
   }
}
</style>
