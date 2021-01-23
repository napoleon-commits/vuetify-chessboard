<template>
    <v-img
    :lazy-src="require('@/images/blankSquare.png')"
    :src="imageSrc"
    :max-width="maxWidthComputed"
    class="ma-auto"
    ></v-img>
</template>

<script>
export default {
    name: 'ChessPieceImage',
    props: ['letter', 'tileWidth', 'tileHeight'],
    data() {
        return {
            innerWidth: null,
            innerHeight: null,
        };
    },
    computed: {
        imageSrc(){
            if(['r','n','b','q','k','p'].includes(this.letter)){
                return require(`@/images/b${this.letter.toUpperCase()}.png`)
            }
            if(['R','N','B','Q','K','P'].includes(this.letter)){
                return require(`@/images/w${this.letter}.png`);
            }
            return require('@/images/blankSquare.png');
        },
        maxWidthComputed(){
            if(this.tileWidth > 47.1766){
                if(this.tileHeight < 43){
                    return this.tileHeight;
                }
                return 47.1766;
            }
            return 20;
        },
    },
    methods: {
        updateWindowWidth(){
            this.innerWidth = window.innerWidth;
            this.innerHeight = window.innerHeight;
        },
    },
    mounted() {
        this.$nextTick(() => {
            this.updateWindowWidth();
        });
        window.addEventListener('resize', this.updateWindowWidth);
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.updateWindowWidth);
    },
}
</script>

<style>

</style>