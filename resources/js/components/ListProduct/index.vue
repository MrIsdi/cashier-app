<template>
    <main>
        <title-cashier name="Semua Produk" />
        <add-product :products="products" />
        <table-cashier :kolom="['Name', 'Description', 'Stock', 'Price']" :products="products" :fungsi="handleAdd" />
    </main>
</template>
<script>
    export default {
        props: ["products"],
        emits: ["add-carts"],
        methods:{
            handleAdd(id){
                this.$emit("add-carts", id)
            },
        }
    }
</script>
