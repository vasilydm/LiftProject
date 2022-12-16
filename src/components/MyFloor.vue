<template>
  <div class="floor">
    <div class="inner-floor"><button>{{ number.id }}</button></div>
  </div>
</template>

<script>

export default {
props: ['number'],
components: {
  
}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kenia&display=swap');
.floor {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  border-top: 1px solid #e2e2a9;
  height: 20%;
  background-color: #393b5a;
}
button {
  font-family: 'Kenia', cursive;
  font-size: 5em;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  background-color: transparent;
  color: #e2e2a9;
  border: none;
  cursor: pointer;
}
.inner-floor {
  position: absolute;
  right: 10px;
}
</style>
