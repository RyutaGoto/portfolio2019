<template lang="pug">
    div.works
        h2 Works
        div.columns.is-multiline.is-centered
            div.column.is-narrow(v-on:click="openModal(lixie.img.item, lixie.title, lixie.detail, lixie.skill)")
                img.item.box(v-bind:src="lixie.img.thum")
            div.column.is-narrow(v-on:click="openModal(amethyst.img.item, amethyst.title, amethyst.detail, amethyst.skill)")
                img.item.box(v-bind:src="amethyst.img.thum")            
            div.column.is-narrow(v-on:click="openModal(caravan.img.item, caravan.title, caravan.detail, caravan.skill)")
                img.item.box(v-bind:src="caravan.img.thum")
            div.column.is-narrow(v-on:click="openModal(yuki.img.item, yuki.title, yuki.detail, yuki.skill)")
                img.item.box(v-bind:src="yuki.img.thum")
            div.column.is-narrow(v-on:click="openModal(gomi.img.item, gomi.title, gomi.detail, gomi.skill)")
                img.item.box(v-bind:src="gomi.img.thum")
            div.column.is-narrow(v-on:click="openModal(dragonfly.img.item, dragonfly.title, dragonfly.detail, dragonfly.skill)")
                img.item.box(v-bind:src="dragonfly.img.thum")
            div.column.is-narrow(v-on:click="openModal(circuit.img.item, circuit.title, circuit.detail, circuit.skill)")
                img.item.box(v-bind:src="circuit.img.thum")
            div.column.is-narrow(v-on:click="openModal(land.img.item, land.title, land.detail, land.skill)")
                img.item.box(v-bind:src="land.img.thum")
            div.column.is-narrow(v-on:click="openModal(logo.img.item, logo.title, logo.detail, logo.skill)")
                img.item.box(v-bind:src="logo.img.thum")
            div.column.is-narrow(v-on:click="openModal(moto.img.item, moto.title, moto.detail, moto.skill)")
                img.item.box(v-bind:src="moto.img.thum")
            div.column.is-narrow(v-on:click="openModal(lamp.img.item, lamp.title, lamp.detail, lamp.skill)")
                img.item.box(v-bind:src="lamp.img.thum")

        //モーダルコンポーネント
        ModalItem(v-on:close="closeModal" v-if="modal")
            template(slot="img")
                carousel(:perPage="1", :navigationEnabled="false", :paginationEnabled="false")
                    slide( v-for="i in imgSrc")
                        span.label
                            img(:src="i")
            template(slot="footer")
                p.title {{ titleSrc }}
                    p.detail {{ detailSrc }}
                        p.skill スキル：{{ skillSrc }}
</template>

<script>
    import Item from './Item.vue'
    import ModalItem from './ModalItem.vue'
    import { swiper, swiperSlide } from 'vue-awesome-swiper'
    import { Carousel, Slide } from 'vue-carousel'
    import yaml from './contents/work.yaml'

    console.log(yaml)
    
    export default {
        name: 'Works',
        data: function(){
            return{
                modal: false,
                imgSrc: [],
                titleSrc: '',
                detailSrc: '',
                skillSrc: '',
                logo:{
                    img:{
                        thum: require('./images/logo/logo_thumnail.jpg'),
                        item: [require('./images/logo/logo_1.jpg'),],
                    },
                    title: 'RyutaGotoのロゴマーク',
                    detail: '自分の名詞を作るときに「自身を構成しているものはなにか。」と考えたときに紙に走り書きし始めたことがきっかけで制作した。',
                    skill: 'Illustrator',
                },
                moto:{
                    img:{
                        thum: require('./images/moto/moto_thumnail.jpg'),
                        item: [require('./images/moto/moto_1.jpg'), require('./images/moto/moto_2.jpg'), require('./images/moto/moto_3.jpg'), require('./images/moto/moto_4.jpg'), require('./images/moto/moto_5.jpg'), require('./images/moto/moto_6.jpg')],
                    },
                    title: 'Moto Fonts',
                    detail: '"no more tofu"をコンセプトにGoogleが2012年に開発したNoto Fontsを見て、"豆腐ってむしろ可愛い形しているし敬遠すべきではないのでは？"と考えた。これを受けて私は実際の文字化けの「豆腐」をベースに"more tofu"をコンセプトとしたMoto Fontsを制作した。最初のバージョンは24時間以内で発案からリリースまでを終えた。',
                    skill: 'Illustrator',
                },
                lamp:{
                    img:{
                        thum: require('./images/lamp/lamp_thumnail.jpg'),
                        item: [require('./images/lamp/lamp_1.jpg'), require('./images/lamp/lamp_2.jpg'), require('./images/lamp/lamp_3.jpg'), require('./images/lamp/lamp_4.jpg'), require('./images/lamp/lamp_5.jpg'), require('./images/lamp/lamp_6.jpg'), require('./images/lamp/lamp_7.jpg'), require('./images/lamp/lamp_8.jpg'), require('./images/lamp/lamp_9.jpg'), ],
                    },
                    title: '光る電源タップ',
                    detail: '私たちの日常は誰かからの恩恵や、自分を支えてくれる何かによって成り立っていることだろう。例えば蛇口をひねれば水が出たり、お金と引き換えに飲食物が提供されたりと…また、今回行う電子工作に欠かせない電気もその一つであると私は捉えた。このように私たちの日常を支えてくれるために当たり前のように存在しているものを軽視しないでほしいという思いを込めて「当たり前のことを当たり前に思わないように」をコンセプトに本作品の制作に取り組んだ。',
                    skill: 'Arduino, 電子工作',
                },
                land:{
                    img:{
                        thum: require('./images/land/land_1.png'),
                        item: [require('./images/land/land_1.png'), require('./images/land/land_2.png'), require('./images/land/land_3.png'), ],
                    },
                    title: '函館市都市景観章のロゴマーク',
                    detail: '函館市で行われている取り組みの1つに「都市景観賞」というものが存在する。このロゴマークは函館市の都市景観賞のweb制作に携わる一環で制作したものだ。この土地に住む人々の営みの様子を8の字のような循環として表した。色は函館山から見える町並みの色をイメージしながら設計した。',
                    skill: 'Illustrator',
                },
                circuit:{
                    img:{
                        thum: require('./images/naiLogo/circuit_1.png'),
                        item: [require('./images/naiLogo/circuit_1.png'), require('./images/naiLogo/circuit_2.png'), ],
                    },
                    title: '【ないロゴ】ポップな電子回路',
                    detail: '実在しない団体やサービス、物語などを想像しながら作るロゴマーク。今回は高専生向け学習アプリ「Circuit」のロゴである。中学校から進学したばかりの期待に胸を膨らませる高専1年生。線だけで描かれた回路図に退屈しないよう、彼らが楽しみながら学習できるようにとデザインを凝らした。(このアプリは実在するものではありません。)',
                    skill: 'Illustrator',
                },
                dragonfly:{
                    img:{
                        thum: require('./images/naiLogo/dragonfly_1.png'),
                        item: [require('./images/naiLogo/dragonfly_1.png'), require('./images/naiLogo/dragonfly_2.png'), require('./images/naiLogo/dragonfly_3.png'), require('./images/naiLogo/dragonfly_4.png'), ],
                    },
                    title: '【ないロゴ】蜻蛉.inc',
                    detail: '実在しない団体やサービス、物語などを想像しながら作るロゴマーク。今回は大手航空機メーカー「蜻蛉.inc」のロゴである。これまで不可能とされていた飛行物体における急旋回や急停止といった動きを実現したのが蜻蛉.incである。そのメカニズムには実際の蜻蛉のありとあらゆる動きを参考にしているとかしていないとか…(この会社は実在するものではありません。)',
                    skill: 'Illustrator',
                },
                gomi:{
                    img:{
                        thum: require('./images/naiLogo/GomiFes_1.png'),
                        item: [require('./images/naiLogo/GomiFes_1.png')],
                    },
                    title: '【ないロゴ】GOMIBAKO FESTIVAL 2019',
                    detail: '実在しない団体やサービス、物語などを想像しながら作るロゴマーク。今回は開催から10年目を迎える「GOMIBAKO FESTIVAL 2019」のロゴマークである。家の中から施設に至るまで様々な場所に存在するゴミ箱。彼らのおかげで私達はゴミにまみれた生活を送らずに済んでいる。このフェスを機会に我々の生活に多大なる恩恵をもたらすゴミ箱の起源や種類などについて触れてみませんか。(このイベントは実在するものではありません。)',
                    skill: 'Illustrator',
                },
                yuki:{
                    img:{
                        thum: require('./images/yuki/yuki_1.png'),
                        item: [require('./images/yuki/yuki_1.png'), require('./images/yuki/yuki_2.png')],
                    },
                    title: '雪んこ茶房のロゴマーク',
                    detail: '「雪んこ茶房」とはアイドルマスターに関連したツールの制作や、アイドルマスターの話をするために集まった任意団体である。制作するにあたり、「雪」と「茶」を意識し、そこから和を感じてもらえるようなテイストを目指した。',
                    skill: 'Illustrator',
                },
                caravan:{
                    img:{
                        thum: require('./images/caravan/caravan_1.png'),
                        item: [require('./images/caravan/caravan_1.png'), ],
                    },
                    title: 'DesignCaravan',
                    detail: '大学の講義の一環で集まったデザイナー集団「DesignCaravan」の紹介Webサイト。制作にあたってのWebサイトのコンセプトから構造、モックアップ、デザイン、実装、公開に至るまでの一連の作業を行った。写真を日々更新するため、コンテンツの追加を行いやすいように工夫も凝らしてある。',
                    skill: 'Illustrator, Xd, Nuxt, Pug, Sass, Firebase, Buefy',
                },
                amethyst:{
                    img:{
                        thum: require('./images/naiLogo/amethyst_1.png'),
                        item: [require('./images/naiLogo/amethyst_1.png'), require('./images/naiLogo/amethyst_2.png'), require('./images/naiLogo/amethyst_3.png')]
                    },
                    title: '【ないロゴ】Amethyst',
                    detail: '実在しない団体やサービス、物語などを想像しながら作るロゴマーク。今回は銀河間を股にかけて活動している停戦監視団「Amethyst」のロゴマークである。西暦3020年、人類の争いは舞台は地球から宇宙に移った。正義とはいつの時代も自身の何かしらに対する愛から芽生える。この愛に溺れ、本来の目的を見失った権力を鎮めるために停戦監視団「Amethyst」はその力を行使する。',
                    skill: 'Illustrator'
                },
                lixie:{
                    img:{
                        thum: require('./images/lixie/lixie_thumnail.png'),
                        item: [require('./images/lixie/lixie_1.png'), require('./images/lixie/lixie_2.png'), require('./images/lixie/lixie_3.png'), require('./images/lixie/lixie_4.png'), require('./images/lixie/lixie_5.png')]
                    },
                    title: 'LIXIE',
                    detail: '1960 年代までかつて数字や文字を表示するためのデバイスとして世界的に量産されていたニキシー管、その特性ゆえの寿命の短さや高電圧を必要とするためLED の登場と共に衰退の一途を辿った。本作品はそのニキシー管を模してアクリル板とLEDで表現した先駆者のオマージュ作品である。',
                    skill: 'Illustrator, Arduino, 電子工作'
                }
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
            openModal(imgTemp, titleTemp, detailTemp, skillTemp){
                this.modal = true
                this.imgSrc = imgTemp
                this.titleSrc = titleTemp
                this.detailSrc = detailTemp
                this.skillSrc = skillTemp
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
    padding-top: 5vh;
    padding-right: auto;
    padding-left: auto;

.works h2
    color: #585858;
    font-size: 25pt;
    margin-top: 5vh;
    margin-bottom: 5vh;
    

//columnの部分
.columns
    width: 100vw;
    margin: 0;
    //background-color: gray;   
    .column
        width: 70vw;
        height: auto;
        margin: 5px auto;
        .item
            border-radius: 20px;
            -webkit-border-radius: 20px;
            -moz-border-radius: 20px;
        .box
            padding: 0;
            box-shadow: 4px 5px 3px rgba(20, 20, 20, 0.2);
            img
                width: 90vw;
                height: 100%;
                object-fit: cover;

//modalの部分
.title
    font-size: 20px;
    text-align: left;
    //margin-bottom: 3px;

.detail
    margin-top: -25px;
    text-align: left;
    font-size: 10pt;

.skill
    margin: 5pt;
    font-size: 11pt;

//vue-carouselの部分
.VueCarousel
    width: 100%;
    margin-top: 0px;
    .VueCarousel-slide
        width: 100%;
        height: 34vh;
        position: relative;
        background: white;
        color: #fff;
        font-family: Arial;
        font-size: 24px;
        text-align: center;
        //height: 33vh;
        //margin-bottom: -30px;
        
        .label
            width: 100%;
            height: 34vh;
            img
                width: 100%;
                height: 34vh;
                object-fit: cover;

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

@media(min-width: 600px)
    .works
        padding-top: 5vh;
        padding-right: auto;
        padding-left: auto;
        h2
            color: #585858;
            font-size: 30pt;
            margin-top: 10vh;
            margin-bottom: 30px;

    //columnの部分
    .columns 
        width: 65vw;
        margin: 0 auto;
        .column
            width: 20vw;
            height: 30vh;
            margin: 3vh auto;
            padding: 0;
            .item
                border-radius: 20px;
                -webkit-border-radius: 20px;
                -moz-border-radius: 20px;
            .box
                padding: 0;
                box-shadow: 4px 5px 3px rgba(20, 20, 20, 0.2);
                margin: 0 auto;
            img
                max-width: 100%;
                max-height: 100%;
                width: 20vw;
                height: 30vh;
                object-fit: cover;

    //modalの部分
    .title
        font-size: 1.4rem;
        text-align: left;
        //margin-bottom: 3px;
    
    .detail
        font-size: 0.9rem;
        margin-top: -15px;
        text-align: left;
    
    .skill
        margin: 5pt;
        font-size: 11pt;
    
    //vue-carouselの部分
    .VueCarousel
        width: 100%;
        .VueCarousel-slide
            position: relative;
            background: white;
            color: #fff;
            font-family: Arial;
            font-size: 24px;
            text-align: center;
            width: 100%;
            height: 45vh;
            .label
                width: 100%;
                height: 45vh;
                img
                    width: 100%;
                    height: 45vh;
                    object-fit: cover;

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
