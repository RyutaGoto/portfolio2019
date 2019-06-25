<template lang="pug">
    div.about
        h2 About
        div.prof
            img(src='./images/RyutaGoto.jpg')
        div.name
            h3.jpn 後藤隆太
            h3 |
            h3.eng RyutaGoto
        div.belong
            p.title-border 所属
            p 公立はこだて未来大学 デザインコース 3年
            p PCN函館 代表
        div.skill
            p.title-border スキル
            p 電子工作(IchigoJam, Arduino)
            p Web(Pug, Sass, Vue.js, Xd)
            p グラフィック(Illustrator, PhotoShop, LightRoom)
        div.footer
            p ©Copyright 2019 RyutaGoto All rights reserved.
    
</template>

<script>
    export default {
        name: 'About',
        data: function(){
            return{};
        },
    }
</script>

<style lang="sass" scoped>
    h2
        color: #585858;
        font-size: 30pt;
        margin-top: 15vh;
    
    .prof img
        height: 18%;
        width: 18%;
        border-radius: 50%;
        margin-top: 3vh;
        margin-bottom: 2vh;

    
    h3
        display: inline;

    .about
        height: 100%;

    .name
        

    .name h3
        margin: 5px;
        font-size: 22pt;
        color: #565656;

    .belong
        margin-top: 20px;    

    .belong p
        font-size: 14pt;
        color: #565656;
        
    .skill
        margin-top: 20px;
        margin-bottom: 40px;

    .skill p
        font-size: 14pt;
        color: #565656;

    .footer
        padding: 2rem 1.5rem 2rem;
        margin-top: 12vh;
        background-color: #325E35;
        color: #FFF5F5;

    .title-border
        display: flex;
        align-items: center;
        font-size: 20pt;

    .title-border:before, .title-border:after
        border-top: 1px solid;
        content: "";
        flex-grow: 1;

    .title-border:before
        margin-right: 1rem;
        margin-left: 30vw;

    .title-border:after
        margin-left: 1rem;
        margin-right: 30vw;
        
</style>
