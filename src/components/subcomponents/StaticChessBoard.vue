<template>
    <div
        :style="`
            padding-top: ${((containerHeight)-(containerHeight*GoldenRatio))/2}px;
            padding-left: ${((containerWidth)-(containerWidth*GoldenRatio))/2}px;
        `"
    >
        <div
            :style="`
                border: 2px solid black;
                width: ${containerWidth*GoldenRatio+4}px;
                height: ${containerHeight*GoldenRatio+4}px;
            `"
        >
            <v-row no-gutters v-for="(rank, i) in 9" :key="rank">
                <v-col
                    :style="`height: ${containerHeight*GoldenRatio/9}px;`"
                    class="text-center" 
                    v-for="(file, j) in 9"
                    :key="file"
                    no-gutters
                >
                    <div :style="`padding-top: ${((containerHeight*GoldenRatio/9)-(16))/2}px`">
                        {{i}}{{j}}
                    </div>
                </v-col>
            </v-row>
        </div>
    </div>
</template>

<script>
import GoldenRatio from '@/static/GoldenRatio';

export default {
    name: 'StaticChessBoard',
    props: ['containerWidth', 'containerHeight'],
    data() {
        return {
            GoldenRatio,
        };
    },
}
</script>

<style>

</style>