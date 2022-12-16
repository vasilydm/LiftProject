<template>
  <div class="app">
    <MyContainer/>
  </div>
</template>

<script>
import MyContainer from './components/MyContainer.vue';
export default {
  components: {
    MyContainer,
  }
}
</script>

<style>
.app {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  background-color: #d6b775;
}
.color1 {color: #1d2106;}
.color2 {color: #154e2d;}
.color3 {color: #d67788;}
.color4 {color: #d6b775;}
.color5 {color: #e2e2a9;}
</style>

