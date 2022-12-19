<template>
<div ref="theVeryFloor" class="floor">

  <div class="numButton">

      <div class="floor-number">{{ floorNumber }}</div>

      <button
        @click="$emit('toggleButton', floorIndex)"
        :style="{'background-color':'#60f93a'}"
        ref="theVeryButton"
      />
  </div>
  
</div>
</template>

<script>

export default {
props: ['floorNumber', 'floorIndex']
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Courier+Prime:wght@700&display=swap');
.floor {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

  display: flex;
  justify-content: center;

  border-top: none;
  box-shadow: inset 0px 1px gold;
  height: 20%;
  background-color: #393b5a;
}

.numButton {
  display: flex;
  align-items: center;
}

button {
  border-radius: 40em;
  cursor: pointer;
  transition: all .15s;
  width: 2em;
  height: 2em;
  margin-left: 1em;
}

button:hover {
  transform: scale(1.125);
}

button:active {
  transform: scale(1.025);
}

.floor-number {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

  font-family: 'Courier Prime', monospace;
  font-size: 5em;
  background-color: transparent;
  color: #e2e2a9;
  border: none;
  cursor: pointer;
}
</style>
