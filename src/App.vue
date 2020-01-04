<template>
  <div>
    <div id="app">
        <h1>{{ carName }}</h1>
        <app-counter
        :counter="counter">
        </app-counter> 
        <app-car 
        @nameChanged="carName=$event"
        @counterUpdated="counter=$event"
        :carName="carName" 
        :carYear="carYear"
        :counter="counter"
        :changeFunc="changeNameToAudi">
        </app-car> 
<hr>
        <app-car 
        @nameChanged="carName=$event"
        @counterUpdated="counter=$event"
        :carName="carName" 
        :carYear="carYear"
        :counter="counter"
        :changeFunc="changeNameToAudi">
        </app-car> 
    </div>
  </div>
</template>

<script>
// import hello from './components/hello.vue'
import Car from "./components/car.vue" 
import Counter from "./components/counter.vue" 

export default {
  name: 'app',
  data () {
      return {
        carName: 'Ford from parent',
        carYear: 2019,
        counter: 0,
      }
  },
  components: {
    // appHello:hello,
    appCar:Car,
    appCounter: Counter
  },
  methods: {
    changeNameToAudi(){
      this.carName = 'Audi'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
