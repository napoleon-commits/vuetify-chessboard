<template>
  <v-container>
    <StaticChessBoard />
  </v-container>
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
