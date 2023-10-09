<script setup lang="ts">

import {Board} from "@/models/Board";
import CellComponent from "@/components/CellComponent.vue";

const props = defineProps<{
  board: Board
}>()

</script>

<template>
  <div class="board">
    <div v-for="(row, index) in props.board.cells" :key="index">
      <div v-for="cell in row" :key="cell.id">
        <cell-component
          :cell="cell"
        />
      </div>
    </div>
  </div>
</template>

<style lang="sass">

</style>