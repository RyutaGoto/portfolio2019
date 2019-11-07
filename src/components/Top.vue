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
    .top 
        height: 80vh;
        display: flex;
        justify-content: center;
        align-items: center;
        img
            height: 25vh;
            margin-bottom: 15px;

        span
            display: block;
            vertical-align: middle;
            color: #DDDDDD;
            font-size: 15pt;
                
    @media(min-width: 600px)
        .top
            height: 70vh;
            padding-top: 20vh;
            img
                vertical-align: middle;
                height: 200px;
                margin-right: 20px;
            span
                display: inline;
                font-size: 33pt;
                margin-left: 20px;

</style>

