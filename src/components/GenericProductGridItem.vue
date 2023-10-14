<script setup>
const props = defineProps({
    picture: String,
    price: Number,
    discount: Number,
    description: String,
    cartLink: String,
    id: Number
})
</script>

<template>
    <div class="col-lg-4 col-md-6 col-sm-6 d-flex">
        <div class="card w-100 my-2 shadow-2-strong">
            <img :src="picture" class="card-img-top" />
            <div class="card-body d-flex flex-column">
                <div v-if="discount > 0" class="d-flex flex-row">
                    <h5 class="mb-1 me-1">{{ (price*(100-discount)/100).toFixed(2) }} Lei</h5>
                    <span class="text-danger"><s>{{ price }} Lei</s></span>
                </div>
                <div v-else class="d-flex flex-row">
                    <h5 class="mb-1 me-1">{{ price }} Lei</h5>
                </div>
                <p class="card-text">{{ description }}</p>
                <div class="card-footer d-flex align-items-end pt-3 px-0 pb-0 mt-auto">
                    <RouterLink :to="'product/' + id">Go to page</RouterLink>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
img.card-img-top {
    width: 150px;
}
</style>
