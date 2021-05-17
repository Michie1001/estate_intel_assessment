<template>
  <QuizTable />
</template>

<script>
import QuizTable from './components/QuizTable.vue'

export default {
  name: 'App',
  components: {
    QuizTable
  }
};
</script>

<style lang="scss">
  @import '@/scss/app.scss';

  #app{
    font-family: Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
