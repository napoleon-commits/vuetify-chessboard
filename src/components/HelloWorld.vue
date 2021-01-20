<template>
  <v-container>
    <StaticChessBoard 
      :pieceString="pieceString"
      :orientation="orientation"
    />
    <div class="my-5">
      <v-btn @click="toggleOrientation">Toggle Orientation</v-btn>
    </div>
  </v-container>
</template>

<script>
  import StaticChessBoard from '@/components/subcomponents/StaticChessBoard';
  import ReverseChessString from '@/utils/ReverseChessString';

  export default {
    name: 'HelloWorld',
    components: {
      StaticChessBoard,
    },
    data() {
      return {
        pieceString: 'rnbqkbnrpppppppp................................PPPPPPPPRNBQKBNR',
        orientation: 'white',
      };
    },
    methods: {
      toggleOrientation() {
        this.orientation = (this.orientation === 'white') ? 'black' : 'white';
        this.pieceString = ReverseChessString(this.pieceString);
      },
    },
  }
</script>
