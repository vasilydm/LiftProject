<template>
  <div class="app">
    <div class="container">
      <div class="building-elevator">

        <MyBuilding
          @toggleButton="onToggleButton"
          ref="myBuilding"
        />

      </div>
    </div>
  </div>
</template>

<script>
import MyBuilding from './components/MyBuilding.vue'
import { gsap } from "gsap";
export default {

provide() {
    return {
      floors: this.floors
    }
  },

data() {
  return {
    floors: [
      {
        id: 5,
        idx: 0,
        isPushed: false,
        isVisited: false,
      },
      {
        id: 4,
        idx: 1,
        isPushed: false,
        isVisited: false,
      },
      {
        id: 3,
        idx: 2,
        isPushed: false,
        isVisited: false,
      },
      {
        id: 2,
        idx: 3,
        isPushed: false,
        isVisited: false,
      },
      {
        id: 1,
        idx: 4,
        isPushed: false,
        isVisited: true,
      },
    ],
    pushedButtons: []
  }
},

methods: {
  onToggleButton(floorIndex) {
    // Получаем объект с нужным этажом
    let checkButton = this.floors.find((item) => {
      return item.idx === floorIndex
    })

    // Проверяем, нужно ли туда запускать лифт
    if (checkButton.isPushed === true || checkButton.isVisited === true) {
      return;
    }

    //Заносим индекс этажа в список ожидания
    this.pushedButtons.push(floorIndex)


    // Забираем нужный номер этажа из очереди
    let shiftedFloor = this.pushedButtons.shift();

    // Получаем этаж, на который едем (html элемент)
    let targetFloor = this.$refs.myBuilding.$refs.myFloor[shiftedFloor].$refs.theVeryFloor;

    
    //Меняем isPushed кнопки целевого этажа
    checkButton.isPushed = true

    //Меняем цвет кнопки целевого этажа на красный
    this.$refs.myBuilding.$refs.myFloor[floorIndex].$refs.theVeryButton.style.backgroundColor = '#f93a3a'

    // Получаем крайнюю верхнюю точку targetFloor
    let topTargetFloor = targetFloor.getBoundingClientRect().top - 7 + 'px';

    //Получаем сам элемент лифта
    let elevator = this.$refs.myBuilding.$refs.myElevator.$refs.theVeryElevator;

    //Получаем покинутый этаж
    let checkVisited = this.floors.find((item) => {
      return item.isVisited === true
    })

    //Меняем состояние покинутого этажа на isVisited: false
    checkVisited.isVisited = false

    //Считаем duration
    let duration = Math.abs(checkButton.id - checkVisited.id);

    //Запускаем лифт
    topTargetFloor += window.scrollY;
    gsap.to(elevator, {top:topTargetFloor, duration:duration})

    //ТАЙМЕР!!!

    //МИГАНИЕ!!!

    //Меняем значение isVisited целевого этажа
    checkButton.isVisited = true

    //Меняем isPushed кнопки целевого этажа
    checkButton.isPushed = false

    //Меняем цвет кнопки целевого этажа на зеленый
    this.$refs.myBuilding.$refs.myFloor[floorIndex].$refs.theVeryButton.style.backgroundColor = '#60f93a'












    }
},

components: {
    MyBuilding,
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
.container {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.building-elevator {
  box-sizing: border-box;
  margin: 0;
  padding: 0;

  display: flex;
}

.color1 {color: #1d2106;}
.color2 {color: #154e2d;}
.color3 {color: #d67788;}
.color4 {color: #d6b775;}
.color5 {color: #e2e2a9;}
.color5 {color: #f93a3a;}
.color5 {color: #60f93a;}
</style>

