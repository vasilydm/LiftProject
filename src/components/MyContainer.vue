<template>
  <div class="container">
    <MyBuildingElevator/>
  </div>
</template>

<script>
import MyBuildingElevator from './MyBuildingElevator.vue';
export default {
  components: {
    MyBuildingElevator,
  }
}
</script>

<style>
.container {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>