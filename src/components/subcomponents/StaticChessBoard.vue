<template>
    <div>
        <v-row v-for="(rank, i) in 8" :key="rank">
            <v-col v-for="(file, j) in 8" :key="file">
                {{pieceString[i*8+j]}}
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    name: 'StaticChessBoard',
    props: ['pieceString', 'orientation'],
}
</script>

<style>

</style>