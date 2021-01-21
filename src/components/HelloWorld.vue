<template>
  <div :style="`background-color: rgba(0,0,0,0.1); height: 100vh; width: 100vw;`">
    <StaticChessBoard />
  </div>
</template>

<script>
  import StaticChessBoard from '@/components/subcomponents/StaticChessBoard';

  export default {
    name: 'HelloWorld',
    components: {
      StaticChessBoard,
    },
  }
</script>
