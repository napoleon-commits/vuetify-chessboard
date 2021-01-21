<template>
    <v-img
    :lazy-src="require('@/images/blankSquare.png')"
    :src="imageSrc"
    ></v-img>
        <!-- :max-height="boardHeight/9"
    :max-width="boardWidth/9" -->
</template>

<script>
import GoldenRatio from '@/static/GoldenRatio';

export default {
    name: 'ChessPieceImage',
    props: ['letter', 'boardWidth', 'boardHeight'],
    data() {
        return {
            GoldenRatio
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
        } 
    }
}
</script>

<style>

</style>