<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain,
    AppFooter
  },
  data() {
    return {
      store
    }
  },
  methods: {
    search() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
        params: {
          // name: store.searchKey,
          // archetype: store.searchArchetype
        }
      })
        .then((response) => {
          console.log(response);
          this.store.cards = response.data.data;
          this.store.cardsFound = response.data.data.length;
        })
        .catch((error) => {
          console.log(error);
          this.store.cards = [];
          this.store.cardsFound = 0;
        })
    }
  },
  created() {
    this.search();
  }
}
</script>

<template>
  <div class="mx-5">
    <AppHeader />
    <AppMain @qualcosa="search" />
    <AppFooter />
  </div>
</template>


<style lang="scss"></style>
