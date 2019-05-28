<template lang="pug">
    img(v-on:click="doAction")

</template>

<script>
    export default {
        name: 'Item',
        data: function(){
            return{};
        },
        props: [ 'thumb' ],
        methods: {
            doAction: function(text){
                this.thumb = './images/' + this.thumb + '.png';
            }
        }   
    }

</script>

<style lang="sass" scoped>

</style>
