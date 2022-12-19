<template>
  <div class="building">

    <MyElevator
      ref="myElevator"
    />
    
    <MyFloor
      v-for="floor in floors"
      :key="floor.id"
      :floorNumber="floor.id"
      :floorIndex="floor.idx"
      @toggleButton="$emit('toggleButton', $event)"
      ref="myFloor"
    />

  </div>
</template>

<script>
import MyElevator from './MyElevator.vue';
import MyFloor from './MyFloor.vue';

export default {

inject: ['floors'],
components: {
  MyFloor,
  MyElevator
}
}

</script>

<style>
.building {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

  position: relative;

  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: rgb(1, 9, 19);
  border-radius: 10px;
  width: 40rem;
  height: 30rem;
}

</style>