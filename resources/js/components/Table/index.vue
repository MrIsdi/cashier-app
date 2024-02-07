<template>
    <div class="table-responsive-md">
        <table class="table table-hover">
            <thead>
                <tr>
                    <th v-for="(data, index) in kolom" :key="index">{{ data }}</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <row-cashier :products="products" :carts="carts" :total="total" :fungsi="handle" />
            </tbody>
        </table>
    </div>
</template>
<script>
    export default {
        props:{
            products:{
                default: []
            },
            carts:{
                default: []
            },
            kolom:{
                require: true
            },
            fungsi:{
                require: true
            },
            total:{
                default: 0
            }
        },
        methods: {
            handle(id){
                this.fungsi(id)
            },
        },
    }
</script>
