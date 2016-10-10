<template>
  <div>
    <div v-for="(food, index) in foods" >
      {{food.name}}
        {{food.price}}
        <button @click="deleteMenu(index)">X</button>
      </div>
      <add-menu :addMenu="addMenu"></add-menu>
  </div>
</template>

<script>
import addMenu from './components/addMenu'

export default {
  components: {
    addMenu
  },
  data () {
    return {
      foods: [{
        name: 'ต้มยำ',
        price: '300'
      },
      {
        name: 'อิอิ',
        price: '300'
      }
    ]
    }
  },
  methods: {
    addMenu: function (name, price) {
      var data = {
        name: name,
        price: price
      }
      this.foods.push(data)
    },
    deleteMenu: function (index) {
      this.foods.splice(index, 1)
    }
  }
}
 </script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
