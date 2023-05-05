<script>
import GuessNum from "./components/GuessNum.vue"
export default {
  components: {
    GuessNum
  }
}
</script>

<template>
  <div class="main">
     <GuessNum />
  </div>
  
</template>

<style scoped>
.main {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>
