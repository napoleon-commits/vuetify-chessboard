<template>
  <div id="board-container" :style="`background-color: rgba(0,0,0,0.1); height: 100vh; width: 100vw;`">
    <StaticChessBoard
      :containerWidth="containerWidth"
      :containerHeight="containerHeight"
    />
  </div>
</template>

<script>
  import $ from 'jquery';
  import StaticChessBoard from '@/components/subcomponents/StaticChessBoard';

  export default {
    name: 'HelloWorld',
    components: {
      StaticChessBoard,
    },
    data() {
      return {
        containerWidth: null,
        containerHeight: null,
      };
    },
    methods: {
      updateContainerDimensions() {
        this.containerWidth = $('#board-container').width();
        this.containerHeight = $('#board-container').height();
      },
    },
    mounted() {
      this.$nextTick(()=>{
        this.updateContainerDimensions();
      });
      window.addEventListener('resize', this.updateContainerDimensions);
    },
    beforeDestroy() {
      window.removeEventListener('resize', this.updateContainerDimensions);
    },
  }
</script>
