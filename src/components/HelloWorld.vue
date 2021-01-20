<template>
  <v-container>
    <StaticChessBoard 
      :pieceString="`rnbqkbnrpppppppp................................PPPPPPPPRNBQKBNR`"
      :orientation="`white`"
    />
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
