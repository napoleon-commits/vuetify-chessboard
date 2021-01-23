<template>
    <v-img
    :lazy-src="require('@/images/blankSquare.png')"
    :src="imageSrc"
    :max-height="maxHeight"
    :max-width="maxWidth"
    class="ma-auto"
    ></v-img>
</template>

<script>
export default {
    name: 'ChessPieceImage',
    props: ['letter', 'maxWidth', 'maxHeight'],
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