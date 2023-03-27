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
            //characters: []
        }
    },

}
</script>

<template>
    <div class="container">
        <div class="row g-3">

            <div class="col-12 col-sm-3" v-for="(card, index) in store.cards">
                <Cards :img="card.data.card_images[index].image_url" :name="card.data.name" :type="card.data.type" />
            </div>

        </div>
    </div>
</template>



<style lang="scss" scoped></style>