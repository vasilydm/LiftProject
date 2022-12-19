<template>
  <div
    class="elevator"
    ref="theVeryElevator"
    :style="{
      bottom: floorHeight * (currentFloor - 1) + 'px',
      transition: `bottom ${duration}s`
    }"
  >
  </div>
</template>

<script>
export default {

data() {
  return {
    currentFloor: 1,
    floorHeight: null,
    duration: 1,
  }
},

mounted() {
  console.log(this.$refs.theVeryElevator.offsetHeight);
  this.floorHeight = this.$refs.theVeryElevator.offsetHeight
},

methods: {
  
}

}

</script>

<style>
.elevator {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

  position: absolute;

  left: 1%;
  bottom: 0;
  border-radius: 10px;
  width: 10%;
  height: 20%;
  background-color: #d67788;
}
</style>