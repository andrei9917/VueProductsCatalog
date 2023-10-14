<script setup>
import GenericProductGridItem from './GenericProductGridItem.vue'
import { database } from './database/database.js'

const props = defineProps({
    type: String
})

var productItems = database.filter((x) => x.type==props.type) //api call /GET/type
</script>

<template>
    <main>
        <div v-for="item in productItems" class="row">
            <GenericProductGridItem
                :picture="item.picture"
                :price="item.price" :discount="item.discount" :description="item.name" :cartLink="item.link" :id="item.id"/>
        </div>
    </main>
</template>

<style>
</style>
