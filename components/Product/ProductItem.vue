<template>
    <div class="product-item" :class="product.status">
        <div class="product-item__body" @click="$emit('click', product.id)">
            <div class="product-item__border-diagonal"></div>
            <div class="product-item__border-left"></div>
            <div class="product-item__border-top"></div>
            <div class="product-item__box">
                <p class="product-item__title">{{ product.title }}</p>
                <h2 class="product-item__name">{{ product.name.title }} <span>{{ product.name.subtitle }}</span></h2>
                <div class="product-item-sostav">
                    <p v-for="item in product.sostav" class="product-item-sostav__item">{{ item }}</p>
                </div>
            </div>
            <div class="product-item__weight">
                <span class="product-item__weight-count">{{ product.weight }}</span>
                <span class="product-item__weight-text">кг</span>
            </div>
        </div>
        <div class="product-item-footer">
            <p class="product-item-footer__info">{{ footer }} <a class="product-item-footer__info-link" @click.prevent="$emit('click', product.id)" href="#">{{ link }}</a></p>
        </div>
    </div>
</template>

<script>
export default {
    name: "ProductItem",
    props: {
        product: Object,
    },
    data() {
        return {
            footer: '',
            link: '',
            status: '',
        }
    },
    methods: {
        statusInfo() {
            this.product.footer.forEach(value => {
                if(this.product.status === value.status) {
                    this.footer = value.text
                    this.link = value.link
                }
            });
        }
    },
    watch: {
        product: {
            handler() {
                this.statusInfo()
            },
            deep: true
        },
    },
    beforeMount() {
        this.statusInfo()
    }
}
</script>

<style lang="scss">
@import "styles/product-item.scss";
</style>
