<template>
    <div class="product">
        <ProductList @click="editStatus" :products="products" class="product__list"></ProductList>
    </div>
</template>

<script>
import ProductList from "@/components/Product/ProductList";

export default {
    name: "Product",
    components: {ProductList},
    methods: {
        editStatus(i) {
            if(this.products[i].status !== 'disabled') {
                this.products[i].status === 'default' ? this.products[i].status = 'selected' : this.products[i].status = 'default'
            }
        }
    },
    data() {
        return {
            products: [
                {
                    id: 0,
                    status: 'default',
                    title: 'Сказочное заморское яство',
                    name: {
                        title: 'Нямушка',
                        subtitle: 'с фуа-гра'
                    },
                    sostav: ['10 порций', 'мышь в подарок'],
                    weight: '0,5',
                    footer: [
                        {
                            status: 'default',
                            text: 'Чего сидишь? Порадуй котэ, купи.',
                            link: 'купи',
                        },
                        {
                            status: 'selected',
                            text: 'Печень утки разварная с артишоками.',
                        },
                        {
                            status: 'disabled',
                            text: 'Печалька, с фуа-гра закончился.'
                        },
                    ]
                },
                {
                    id: 1,
                    status: 'selected',
                    title: 'Сказочное заморское яство',
                    name: {
                        title: 'Нямушка',
                        subtitle: 'с рыбой'
                    },
                    sostav: ['40 порций', '2 мыши в подарок'],
                    weight: '2',
                    footer: [
                        {
                            status: 'default',
                            text: 'Чего сидишь? Порадуй котэ, купи.',
                            link: 'купи',
                        },
                        {
                            status: 'selected',
                            text: 'Головы щучьи с чесноком да свежайшая сёмгушка.',
                        },
                        {
                            status: 'disabled',
                            text: 'Печалька, с рыбой закончился.'
                        },
                    ]
                },
                {
                    id: 2,
                    status: 'disabled',
                    title: 'Сказочное заморское яство',
                    name: {
                        title: 'Нямушка',
                        subtitle: 'с курой'
                    },
                    sostav: ['100 порций', '5 мышей в подарок', 'заказчик доволен'],
                    weight: '5',
                    footer: [
                        {
                            status: 'default',
                            text: 'Чего сидишь? Порадуй котэ, купи.',
                            link: 'купи',
                        },
                        {
                            status: 'selected',
                            text: 'Филе из цыплят с трюфелями в бульоне.',
                        },
                        {
                            status: 'disabled',
                            text: 'Печалька, с курой закончился.'
                        },
                    ]
                }
            ]
        }
    }
}
</script>

<style scoped lang="scss">
@import "styles/product.scss";
</style>
