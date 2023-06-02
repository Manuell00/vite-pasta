<script>
export default {
    name: "ProductCard",
    props: {
        details: Object
    }
}
</script>

<template>
    <!-- Blocco Prodotto (Scopongo in componente figlio) -->
    <div class="prod-card">
        <img :src="details.src" :alt="details.titolo">
        <h3>{{ details.titolo }}</h3>
    </div>
</template>


<!-- Aggiungo lo scoped perchè lo stile ci interessa solo per il componente relativo -->
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.prod-card {
    flex-basis: 25%;
    padding: 20px;
    background-color: white;
    border: 2px solid lighten($primary, 70%);

    h3 {
        color: $primary;
    }

    .img {
        display: block;
    }
}
</style>
