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
                width: ${containerWidth*GoldenRatio}px;
                height: ${containerHeight*GoldenRatio}px;
            `"
        >
            <div>
                containerWidth: {{containerWidth}} ; containerHeight: {{containerHeight}}
            </div>
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