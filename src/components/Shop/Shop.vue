<template>
    <div class="container mt-5">
        <div class="row">
            <div class="col-6 ">
                <Goods/>
            </div>
            <div class="col-6">
                <Cart/>
            </div>
        </div>
    </div>
</template>

<script>
    import './Shop.sass';
    import Cart from "@/components/Shop/Cart/Cart";
    import Goods from "@/components/Shop/Goods/Goods";
    import store from "@/components/Shop/ShopStore/store";
    import {mapActions} from 'vuex'
    export default {
        store,
        components:{
            Cart,
            Goods,
        },
        computed: {
            ...mapActions([
                'getRating'
            ])
        },
        mounted(){
            this.$store.dispatch('getRating');
        }
    }
</script>

