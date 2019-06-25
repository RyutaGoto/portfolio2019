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
        height: 200px;
        margin-right: 20px;

    .top span
        vertical-align: middle;
        font-size: 30pt;
        color: #DDDDDD;
        margin-right: 20px;

</style>

