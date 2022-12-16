<template>
  <div class="building">
    <MyFloor
      v-for="floor in floors"
      :key="floor.id"
      :number="floor"
    />
  </div>
</template>

<script>
import MyFloor from './MyFloor.vue';
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
    MyFloor,
  }
}
</script>

<style>
.building {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-color: rgb(1, 9, 19);
  border-radius: 10px;
  width: 40rem;
  height: 30rem;
}
</style>