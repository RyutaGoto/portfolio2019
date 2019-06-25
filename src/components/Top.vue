<template lang="pug">
    div.top
        p 
            img(src="./images/logo.png")
            span RyutaGoto's Portfolio
</template>

<script>
    export default {
        name: 'Top',
        data: function(){
            return{};
        },
        
    }
</script>

<style lang="sass" scoped>
    .top img
        vertical-align: middle;
        height: 150px;

    .top span
        vertical-align: middle;
        font-size: 27pt;
        color: #FFF6F6;

</style>

