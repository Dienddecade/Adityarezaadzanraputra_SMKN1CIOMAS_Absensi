<script lang="ts" setup>
import { useProductsStore } from "~/stores/products";

definePageMeta({
    middleware: ["user-access"]
});

const productStore = useProductsStore();
const allProducts = ref([]);

productStore.getAllProducts().then(() => {
    allProducts.value = productStore.products;
});

const selectedCategory = ref("");
</script>


<template>
    <section>
        <div class="container">
            <div class="py-10">
                <div class="mb-6 flex justify-end gap-6">

                    <NuxtLink to="/product/create"
                        class="text-base bg-blue-600
px-6 py-2 text-white rounded-lg hover:bg-blue-600">Absen Kelas
                    </NuxtLink>
                    
                </div>
                <div class="flex gap-6 flex-wrap mx-auto">
                    <template v-for="(item, index) in allProducts" :key="index">
                        <CardsCardProduct :product="item" class="w-[calc(100%/4-18px)]" />
                    </template>
                </div>
            </div>
    </div>
</section></template> 