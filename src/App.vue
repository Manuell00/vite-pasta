<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import ListProducts from './components/ListProducts.vue'

export default{
  components: {
    AppHeader,
    AppFooter,
    ListProducts
  },

  // Inserisco i dati
  data() {
        return {

            // Ogni singolo oggetto ha le informazioni riguardanti il link relativo
            // Il current serve per gestire a classe active
            menu: [
                {
                    text: "Home",
                    url: "#",
                    current: false
                },
                {
                    text: "Prodotti",
                    url: "#",
                    current: true
                },
                {
                    text: "Chi Siamo",
                    url: "#",
                    current: false
                },
                {
                    text: "Contatti",
                    url: "#",
                    current: false
                },

            ]
        }
    }
}
</script>

<template>
  <!-- Siccome i dati sono nel padre, quello che facciamo è chiamare la props links in modo da non dover modificare AppHeader, in modo che possa ciclare lo stesso -->
  <!-- In questo caso in AppHeader quando lo istanzi gli passi menu come links  -->
  <AppHeader :links="menu"/>

  <main>
    <ListProducts/>
  </main>
  
  <AppFooter/>
</template>

<style lang="scss" >
@use './styles/general.scss' as *;
@use './styles/partials/variables.scss' as *;

h1,
h2,
h3,
h4,
h5,
h6 {
  color: $primary;
}
</style>
