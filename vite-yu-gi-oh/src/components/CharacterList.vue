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
            <div class="col-12 col-sm-3" v-for="card in store.cards">
                <Cards :img="card.data.data.card_image.image_url" :name="card.data.data.name" :type="card.data.data.type" />
            </div>
        </div>
    </div>
</template>



<style lang="scss" scoped></style>