<template>
  <div class="building-elevator">
    <MyElevatorShaft/>
    <MyBuilding/>
  </div>
</template>

<script>
import MyBuilding from './MyBuilding.vue';
import MyElevatorShaft from './MyElevatorShaft.vue';
export default {
  components: {
    MyBuilding,
    MyElevatorShaft,
  }
}
</script>

<style>
.building-elevator {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  display: flex;
}
</style>