<script setup>
import { database } from './database/database.js'

const props = defineProps({
    id: String
})

var item = database.find((x) => x.id==props.id)

var picture = item.picture
var price = item.price
var discount = item.discount
var title = item.name
var cartLink = item.link
var description = item.description
var extraInfo = ["Type: Regular", "Color: Brown", "Material: Cotton, Jeans", "Brand: Reebook"]
</script>

<template>
    <section class="py-5">
        <div class="container">
            <div class="row gx-5">
                <aside class="col-lg-6">
                    <div class="border rounded-4 mb-3 d-flex justify-content-center">
                        <img style="max-width: 100%; max-height: 100vh; margin: auto;" class="rounded-4 fit"
                            :src="picture" />
                    </div>
                </aside>
                <main class="col-lg-6">
                    <div class="ps-lg-3">
                        <h4 class="title text-dark">
                            {{title}}
                        </h4>

                        <span class="h5">{{ (price*(100-discount)/100).toFixed(2) }} Lei</span>

                        <p>
                            {{ description }}
                        </p>

                        <div class="row">
                            <dt class="col-3">Type: Regular</dt>

                            <dt class="col-3">Color: Brown</dt>

                            <dt class="col-3">Material: Cotton, Jeans</dt>

                            <dt class="col-3">Brand: Reebook</dt>
                        </div>

                        <hr />

                        <div class="row mb-4">
                            <div class="col-md-4 col-6 mb-3">
                                <label class="mb-2 d-block">Quantity</label>
                                <div class="input-group mb-3" style="width: 170px;">
                                    <input type="text" class="form-control text-center border border-secondary"
                                        placeholder="14" aria-label="Example text with button addon"
                                        aria-describedby="button-addon1" />
                                </div>
                            </div>
                        </div>
                        <a :href="cartLink" class="btn btn-warning shadow-0"> Buy now </a>
                        <br />
                        <a :href="cartLink" class="btn btn-primary shadow-0"> <i class="me-1 fa fa-shopping-basket"></i> Add to cart
                        </a>
                        <br />
                        <a href="#" class="btn btn-light border border-secondary py-2 icon-hover px-3"> <i
                                class="me-1 fa fa-heart fa-lg"></i> Save </a>
                    </div>
                </main>
            </div>
        </div>
    </section>
</template>

<style>

</style>
