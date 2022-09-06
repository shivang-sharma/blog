<template>
    <div>
        <Facebook :large="large" />
        <Twitter :large="large" />
        <Reddit :large="large" />
        <Linkedin :large="large" />
    </div>
</template>

<script>
import Facebook from './Facebook'
import Linkedin from './Linkedin'
import Reddit from './Reddit'
import Twitter from './Twitter'


export default {
    components: {
        Facebook,
        Linkedin,
        Reddit,
        Twitter
    },
    data () {
        return {
            nuxt: true,
            data: "Our Ailing Planet"
        }
    },
    props: {
        slug:"",
        large: false,
    },
    methods: {
        openShare(){
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