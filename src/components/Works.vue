<template lang="pug">
    div.works
        //<Item/>
        //<Item/>
        //<Item/>
        //<Item/>
        div.columns
            div.column.card(v-on:click="openModal(lampSrc)")
                img.item(v-bind:src="lampSrc")
            div.column.card(v-on:click="openModal(motoSrc)")
                img.item(v-bind:src="motoSrc")
            div.column.card(v-on:click="openModal(logoSrc)")
                img.item(v-bind:src="logoSrc")
        div.columns
            div.column.card(v-on:click="openModal(landSrc)")
                img.item.column(v-bind:src="landSrc")
            div.column.card
            div.column.card

        //モーダルコンポーネント
        //Thumbs Gallery With Loop Mode
        //div.modal
        ModalItem(v-on:close="closeModal" v-if="modal")
            //img(:src="imgSrc")
            carousel(:perPage="1" style="margin-top:0.4rem;" :navigationEnabled="true" )
                slide
                    span.label
                        img(:src="imgSrc")
                slide
                    span.label
                        img(:src="logoSrc")
                slide
                    span.label
                        img(:src="landSrc")
</template>

<script>
    import Item from './Item.vue'
    import ModalItem from './ModalItem.vue'
    import { swiper, swiperSlide } from 'vue-awesome-swiper'
    import { Carousel, Slide } from 'vue-carousel'


    export default {
        name: 'Works',
        data: function(){
            return{
                modal: false,
                message: '',
                next:"next",
                prev:"prev",
                imgSrc: require('./images/moto.png'),
                logoSrc: require('./images/logo_clear(250×250).png'),
                motoSrc: require('./images/moto.png'),
                lampSrc: require('./images/lamp_2.png'),
                landSrc: require('./images/land.png'),
            };
        },
        components: {
            Item,
            ModalItem,
            swiper,
            swiperSlide,
            Carousel,
            Slide,
        },
        methods: {
            openModal(temp){
                this.modal = true
                this.imgSrc = temp
                //this.message = temp
                console.log(this.imgSrc)
            },
            closeModal(){
                this.modal = false
            },
            doSend(){
                if(this.message.length > 0){
                    alert(this.message)
                    this.message = ''
                    this.closeModal()
                }
                else{
                    alert('メッセージを入力してください')
                }
            },
        },
    }
</script>



<style lang="sass" scoped>
    .works
        padding: 50px;

    .column
        margin: 10px;
    
    .card
        padding: 0px 0px;
    
    //vue-carouselの部分
    .VueCarousel
        margin-left: 15%;
        margin-right: 15%;

    .VueCarousel-slide
        position: relative;
        background: white;
        color: #fff;
        font-family: Arial;
        font-size: 24px;
        text-align: center;
        height: 300px;

    .label
        position: relative;
        top: 50%;
        left: 50%;
        transform: translate(-50%, - 50%);

    .header
        text-align: center;
        margin-bottom: 1px;
        padding-top: 15px;
        background: #fff;
        height:  50px;
        min-width: 100%;

    .container
        padding-left: 0;
        padding-right: 0;
        text-align: center;
    
    .subtitle
        box-sizing: border-box;
        display: inline-block;
        margin: 0 auto;
        border-radius: 1.2rem;
        color: #5ebaba;
        border: 2px solid #5ebaba;
        background: #ffffff;
        line-height: 2.4rem;
        padding: 0 1rem;
        position: relative;
        cursor: pointer;
    
</style>
