<template>
    <div>
        <v-row v-for="(rank, i) in 9" :key="rank">
            <v-col v-for="(file, j) in 9" :key="file">
                <span v-if="coordinates[orientation][`${i}${j}`]">
                    {{coordinates[orientation][`${i}${j}`]}}
                </span>
                <span v-else>
                    {{pieceString[i*8+(j-1)]}}
                </span>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    name: 'StaticChessBoard',
    props: ['pieceString', 'orientation'],
    data(){
        return {
            coordinates: {
                white: {
                    '00': 8,
                    '10': 7,
                    '20': 6,
                    '30': 5,
                    '40': 4,
                    '50': 3,
                    '60': 2,
                    '70': 1,
                    '80': '.',
                    '81': 'a',
                    '82': 'b',
                    '83': 'c',
                    '84': 'd',
                    '85': 'e',
                    '86': 'f',
                    '87': 'g',
                    '88': 'h',
                }
            },
        }
    },
}
</script>

<style>

</style>