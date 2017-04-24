<template>
    <div id="app" style="text-align:center">
        <img src="./assets/logo.png">
        <pages :total="total" :current="current" @jump="jump"></pages>
    </div>
</template>

<script>
    import pages from './pages.vue'
    export default {
        data() {
            return {
                total: 1230,
                current: 23
            }
        },
        components: {
            pages
        },
        methods:{
            jump(num){
                this.current = num
            }
        }
    }
</script>