<template>
    <div class="product-list">
        <h1 class="product-list__title">Ты сегодня покормил кота?</h1>
        <div class="product-list__body">
            <ProductItem @click="$emit('click', $event)" class="product-list__item" :product="item"
                         v-for="item in products"
                         :key="item.id"></ProductItem>
        </div>
    </div>
</template>

<script>
import ProductItem from "@/components/Product/ProductItem";

export default {
    name: "ProductList",
    components: {ProductItem},
    props: {
        products: Array,
    },
}
</script>

<style scoped lang="scss">
@import "styles/product-list.scss";
</style>
