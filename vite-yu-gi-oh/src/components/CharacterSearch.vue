<script>
import { store } from '../store';
export default {
    name: 'Search',
    data() {
        return {
            store
        }
    },
    methods: {
        cerca() {
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then((arch) => {
                    console.log(arch);
                    this.store.archetype = arch.archetype_name;

                })
        }
    }
}
</script>

<template>
    <div class="container">
        <form @submit.prevent="$emit('cerca')">
            <div class="row justify-content-center g-1">
                <div class="mb-3 col-12 col-sm-auto">
                    <label for="search-cards" class="form-label d-none">Search Cards</label>
                    <input type="text" class="form-control" id="search-character" placeholder="Search Cards"
                        v-model="store.searchKey">
                </div>
                <div class="mb-3 col-12 col-sm-auto">
                    <label for="search-type" class="form-label d-none">Select Type</label>
                    <select class="form-select" id="search-status" v-model="store.searchStatus">
                        <option selected>Select Type</option>

                        <option v-for="archetipi in store.archetype">
                            {{ archetipi.archetype_name }}
                        </option>

                    </select>
                </div>
                <div class="mb-3 col-12 col-sm-auto">
                    <button type="submit" class="btn btn-primary me-1">Search</button>
                    <button type="reset" class="btn btn-secondary">Reset</button>
                </div>
            </div>
        </form>
    </div>
</template>

<style lang="scss" scoped></style>