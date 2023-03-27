<script>
export default {
    name: 'Search'
}
</script>

<template>
    <div class="container">
        <form>
            <div class="row justify-content-center g-1">
                <div class="mb-3 col-12 col-sm-auto">
                    <label for="search-cards" class="form-label d-none">Search Cards</label>
                    <input type="text" class="form-control" id="search-character" placeholder="Search Cards">
                </div>
                <div class="mb-3 col-12 col-sm-auto">
                    <label for="search-type" class="form-label d-none">Select Type</label>
                    <select class="form-select" id="search-status">
                        <option selected>Select Type</option>
                        <option value="1">Monster</option>
                        <option value="2">Spell</option>
                        <option value="3">Trap</option>
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