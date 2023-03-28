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
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response) => {
        console.log(response);
        this.store.cards = response.data.data;
        this.store.cardsFound = response.data.data.length;
      })
  }
}
</script>

<template>
  <div class="mx-5">
    <AppHeader />
    <AppMain />
    <AppFooter />
  </div>
</template>


<style lang="scss"></style>
