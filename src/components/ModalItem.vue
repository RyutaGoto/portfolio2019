<template lang="pug">
    transition#modal
        div.modal.modal-overlay(@click.self="$emit('close')")
            div.modal-window
                div.modal-content
                    slot(name="img")
                footer.modal-footer
                    //button(v-on:click="confirm(val)") 確認
                    slot#footer(name="footer")
                        button(v-on:click="$emit('close')") Close
</template>

<script src="../dist/js/swiper.min.js"></script>

<script>
    export default {
        name: 'ModalItem',
        data: function(){
            return{
            }
        },
        methods: {
        },
    }
</script>


<style lang="sass" scoped>
    .modal
        &.modal-overlay
            display: flex;
            align-items: center;
            justify-content: center;
            position: fixed;
            z-index: 30;
            top: 0;
            left: 0;
            width: 100%
            height: 100%
            background: rgba(0, 0, 0, 0.5);
        
        &-window
            background: #fff;
            border-radius: 4px;
            overflow: hidden;
            width: 70%;

        &-content
            padding: 10px 20px;

        &-footer
            background: #ccc;
            padding: 30px;
            text-align: right;

    //オーバーレイのトランジション
    .modal-enter-active, .modal-leave-active
        transition: opacity 0.4s;
        
        //オーバーレイに包含されているモーダルウィンドウのトランジション
        .modal-window
            transiotion: opacity 0.4s, transform 0.4s;

    //ディレイを付けるとモーダルウィンドウが消えた後にオーバーレイが消える
    .modal-leave-active
        transition: opacity 0.6s ease 0.4s;

    .modal-enter, .modal-leave-to
        opacity: 0;
        .modal-window
            opacity: 0;
            transform: translateY(-10px);
</style>

