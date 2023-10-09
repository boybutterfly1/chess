<script setup lang="ts">
import {onMounted, ref} from "vue";
import {Board} from "@/models/Board";
import BoardComponent from "@/components/BoardComponent.vue";

const board = ref(new Board())
const restart = () => {
  const newBoard = new Board();
  newBoard.initCells()
  board.value = newBoard
}
onMounted(() => {
  restart()
})
</script>
<template>
  <div class="app">
  <board-component :board="board" />
  </div>
</template>

<style lang="sass">
*
  margin: 0
  padding: 0
.app
  width: 100vw
  height: 100vh
  display: flex
  justify-content: center
  align-items: center
.board
  width: calc(64px * 8)
  height: calc(64px * 8)
  display: flex
  flex-wrap: wrap
.cell
  width: 64px
  height: 64px
  display: flex
  justify-content: center
  align-items: center
.black
  background-color: #5d3405
.white
  background-color: #c9ad86
</style>