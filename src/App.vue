<template>
  <Header />
</template>

<script>
import Header from './components/Header.vue';

export default {
  name: 'PlanetsApp',
  components:{
    Header
  }
}
</script>

<style>
  body{
   margin: 0px;
   background-image: url('./assets/background.svg');
   font-family: 'Spartan';
  }
  div {
    display: flex;
    align-items: center;
  }
</style>
