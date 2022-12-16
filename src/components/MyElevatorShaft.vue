<template>
  <div class="elevator-shaft">
    <MyElevatorFloor
      v-for="floor in floors"
      :key="floor.id"
    />
    <MyElevator/>
  </div>
</template>

<script>
import MyElevatorFloor from './MyElevatorFloor.vue';
import MyElevator from './MyElevator.vue'
export default {
  data() {
    return {
      floors: [
        {
          id: 5,
        },
        {
          id: 4,
        },
        {
          id: 3,
        },
        {
          id: 2,
        },
        {
          id: 1,
        },
      ]
    }
  },
  components: {
    MyElevatorFloor,
    MyElevator,
  },
}
</script>

<style>
.elevator-shaft {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  position: relative;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: rgb(40, 82, 133);
  border-radius: 10px;
  width: 4rem;
  height: 30rem;
}
</style>