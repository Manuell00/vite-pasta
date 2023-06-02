<script>

export default {
    name: "AppHeader",

    // Inserisco la props, quindi ciò che viene passato a links dal padre
    props: {
        links: Array
    }
}
</script>

<template>

    <!-- HEADER -->
    <header>
        <a href="/" class="brand">
            <img src="/logo.png" alt="La Molisana">
        </a>

        <nav>
            <ul>
                <!-- Ciclo all'interno della lista links, Inserisco l'url ed eventualmente la classe active -->
                <li v-for="link in links">
                    <a :href="link.url" :class="link.current ? 'active' : ''">
                        {{ link.text }}
                    </a>

                        <!-- Posso scrivere la riga sopra anche come segue
                        <a href="link.url" :class="{ active: link.current }">
                            {{ link.text }}
                        </a> -->
                </li>
                
            </ul>
        </nav>
    </header>

</template>


<!-- Aggiungo lo scoped perchè lo stile ci interessa solo per il componente relativo -->
<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;
@use '../styles/partials/mixins.scss' as *;


header {
    text-align: center;

    ul {
        list-style: none;
        margin: 2.5rem 1rem 4rem;
        @include center();

        li a {
            display: inline-block;
            padding: 1rem;
            text-decoration: none;
            font-weight: 600;
            transition: background 0.3s;

            &:active,
            &:hover {
                background: lighten($primary, 70%);
            }
        }
    }
}
</style>
