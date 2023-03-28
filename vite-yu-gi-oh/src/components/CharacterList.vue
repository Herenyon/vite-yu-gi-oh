<script>
import { store } from '../store';
import Cards from './Cards.vue';
export default {
    name: 'CharacterList',
    components: {
        Cards
    },
    data() {
        return {
            store,

        }
    },

}

</script>

<template>
    <div class="container">
        <div class="row g-3">

            <div class="col-12 col-sm-3" v-for="card in store.cards.slice(0, 50)">


                <Cards :img="card.card_images.image_url_small" :name="card.name" :type="card.type" />


            </div>

        </div>
    </div>
</template>



<style lang="scss" scoped></style>