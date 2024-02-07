<template>
    <main>
        <title-cashier name="Keranjang Belanja" />
        <table-cashier :kolom="['Name', 'Quantity', 'Price']" :carts="carts" :fungsi="handleDelete" :total="total" />
        <struk-pembayaran :total="total" />
    </main>
</template>
<script>
    export default {
        props: ["carts", "total"],
        emits: ["delete-carts"],
        methods:{
            handleDelete(id){
                this.$emit("delete-carts", id)
            }
        }
    }
</script>
