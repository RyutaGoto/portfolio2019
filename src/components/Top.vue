<template lang="pug">
    div.top
        p 
            img(src="./images/logo_top.png")
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
        height: 25vh;
        margin-bottom: 15px;
        @media(min-width: 600px)
            height: 200px;
            margin-right: 20px;

    .top span
        display: block;
        vertical-align: middle;
        color: #DDDDDD;
        font-size: 15pt;
        @media(min-width: 600px)
            display: inline;
            font-size: 30pt;
            margin-right: 20px;

</style>

