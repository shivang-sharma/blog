<template>
    <v-btn
        icon
        @click="openRedditShare()"
    >
        <v-icon :large="large" style="color: #ff4500">mdi-reddit</v-icon>
    </v-btn>
</template>

<script>
export default {
    data () {
        return {
            nuxt: true,
            data: "Our Ailing Planet"
        }
    },
    props: {
        slug:"",
        large:false,
    },
    methods: {
        openRedditShare(){
            //var url = 'https://www.facebook.com/sharer.php?display=popup';
            //var options = 'toolbar=0,status=0,resizable=1,width=626,height=436';
            //window.open(url,'sharer',options);
            //window.open("http://www.facebook.com/sharer/sharer.php");
            //https://javascript.info/popup-windows
            //https://www.smashingmagazine.com/2020/01/data-components-vue-js/
            window.open('https://www.facebook.com/sharer/sharer.php','facebook-share-dialog','width=626,height=436');
            return false;
        }
    }
    
}
</script>

<style scoped>

</style>