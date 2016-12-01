<template>
    <div class="seller" id="seller">
        我是{{seller.description}}
    </div>
</template>

<script>
    export default {
        props: {
            seller: {
                type: Object
            }
        },
        data () {
            return {
                msg: 'seller'
            };
        },
        created () {
            this.$http.get('/api/seller').then((res) => {
                this.seller.description = 'nsdfiohsduafhsaduifhsduia';
            });
        }
    };
</script>

<style media="screen">

</style>
