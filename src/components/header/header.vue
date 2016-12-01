<template>
    <div class="header" id="header">
        <div class="content-wrapper">
            <div class="avatar">
                <img :src="seller.avatar" width="64" height="64" alt="" />
            </div>
            <div class="bulletin-wrapper">
                <div class="title">
                    <span class="brand"></span>
                    <span class="name">{{seller.name}}</span>
                </div>
                <div class="description">
                    <span class="description">{{seller.description}}/{{seller.deliveryTime}}分钟送达</span>
                </div>
                <div v-if="seller.supports" class="supports">
                    <span class="icon"></span>
                    <span class="text">{{seller.supports[0].description}}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            seller: {
                type: Object
            }
        },
        created () {
        }
    };
</script>

<style media="screen" lang="stylus" rel="stylesheet/stylus">
    .header
        color: #fff
        background: #000
        .content-wrapper
            padding: 24px 12px 18px 24px
            .avatar
                display: inline-block
</style>
