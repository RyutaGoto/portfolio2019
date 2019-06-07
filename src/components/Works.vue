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
            div.swiper-container.gallery-top
                div.swiper-wrapper
                    div.swiper-slide(:style="{backgroundImage:'url(' + 'http://lorempixel.com/1200/1200/nature/10/' + ')' }")
                        //img(:src="imgSrc")
                    div.swiper-slide
                        //(:style="{backgroundImage:'url(' + logoSrc + ')' }")
                        img(:src="motoSrc")
                    div.swiper-slide
                        //(:style="{backgroundImage:'url(' + lampSrc + ')' }")
                        img(:src="lampSrc")
                    div.swiper-slide
                        //(:style="{backgroundImage:'url(' + motoSrc + ')' }")
                        img(:src="landSrc")
                div.swiper-button-next.swiper-button-white
                div.swiper-button-prev.swiper-button-white
            //div.swiper-container.gallery-thumbs
                div.swiper-wrapper
                    div.swiper-slide
                        img(:src="imgSrc")
                    div.swiper-slide
                        img(:src="motoSrc")
                    div.swiper-slide
                        img(:src="lampSrc")
                    div.swiper-slide
                        img(:src="landSrc")           
</template>

<script>
    import Item from './Item.vue'
    import ModalItem from './ModalItem.vue'
    import { swiper, swiperSlide } from 'vue-awesome-swiper'


    export default {
        name: 'Works',
        data: function(){
            return{
                modal: false,
                message: '',
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
            swiperSlide
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

    .swiper-container 
      width: 100%;
      height: 300px;
      margin-left: auto;
      margin-right: auto;
    
    .swiper-slide
      background-size: cover;
      background-position: center;
    
    .gallery-top
      height: 80%;
      width: 100%;
    
    .gallery-thumbs
      height: 20%;
      box-sizing: border-box;
      padding: 10px 0;
    
    .gallery-thumbs .swiper-slide
      height: 100%;
      opacity: 0.4;
    
    .gallery-thumbs .swiper-slide-thumb-active
      opacity: 1;
    
    
</style>
