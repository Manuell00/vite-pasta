<script>

export default {
    name: "AppFooter",
    methods:{

        // Inserisco il metodo per inserire successivamente l'immagine
        getImageURL: function(imgPath) {
            return new URL(imgPath, import.meta.url).href
        }
    }
}
</script>

<template>
    <footer>
        <div class="cols container">
            <a class="logo" href="/">
                <img src="/logo.png" alt="La Molisana">
            </a>

            <div class="footer-links">
                <h4>Pastificio</h4>
                <nav>
                    <ul>
                        <li><a href="#">Il Pastificio</a></li>
                        <li><a href="#">Il Grano</a></li>
                        <li><a href="#">Filiera</a></li>
                        <li><a href="#">100 anni di pastificio</a></li>
                        <li><a href="#"></a>Sartoria della signora</li>
                    </ul>
                </nav>
            </div>


            <div class="footer-links">
                <h4>Prodotti</h4>
                <nav>
                    <ul>
                        <li><a href="#">Le Classiche</a></li>
                        <li><a href="#">Le Integrali</a></li>
                        <li><a href="#">Le Speciali</a></li>
                        <li><a href="#">Le Biologiche</a></li>
                        <li><a href="#"></a>Le Gluten Free</li>
                    </ul>
                </nav>
            </div>
        </div>

        <!-- Richiamo l'immagine attraverso il metodo -->
        <img :src="getImageURL('../assets/images/footer.jpg')" alt="Footer-image">

    </footer>
</template>


<!-- Aggiungo lo scoped perchè lo stile ci interessa solo per il componente relativo -->
<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

footer {
    padding-top: 3rem;

    .cols {
        display: flex;
        margin-bottom: 3rem;

        .logo,
        .footer-links {
            flex-basis: calc(100% / 3);
            padding: 0 1rem;
        }

        h4 {
            text-transform: uppercase;
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        ul {
            list-style: none;

            li a {
                display: inline-block;
                margin-bottom: 0.25rem;
                text-decoration: none;
                font-size: 0.875em;

                &:hover {
                    color: $primary;
                }
            }
        }
    }
}
</style>
