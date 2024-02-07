<template>
    <template v-if="products.length > 0">
        <tr v-for="product in products" :key="product.id">
            <td>{{ product.name }}</td>
            <td>{{ product.desc }}</td>
            <td>{{ product.stock }}</td>
            <td>Rp. {{ product.price }}</td>
            <td v-if="product.stock > 0">
                <button type="button" class="btn btn-primary" v-on:click="handle(product.id)">Add to cart</button>
            </td>
        </tr>
    </template>
    <template v-else>
        <template v-if="carts.length > 0">
            <tr v-for="cart in carts" v-bind:key="cart.id">
                <td>{{ cart.name }}</td>
                <td>{{ cart.quantity }}</td>
                <td>Rp. {{ cart.price }}</td>
                <td>
                    <button type="button" class="btn btn-danger" v-on:click="handle(cart.id)">Delete</button>
                </td>
            </tr>
        </template>
        <tr v-else>
            <td colspan="4">
                <p class="text-center">Produk belum ada</p>
            </td>
        </tr>
        <tr>
            <th colspan="2">Total:</th>
            <th colspan="2">Rp. {{ total }}</th>
        </tr>
    </template>
</template>
<script>
    export default {
        props:{
            products: {
                default: []
            },
            carts: {
                default: []
            },
            total: {
                default: 0
            },
            fungsi:{
                require: true
            }
        },
        methods: {
            handle(id){
                this.fungsi(id)
            }
        },
    }
</script>
