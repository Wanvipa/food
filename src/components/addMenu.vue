<template>
  <div>
    Name: <input v-model="name"><br>
    Price: <input v-model="price"><br>
    <button @click="addMenu(name,price)">submit</button>

  </div>
</template>

<script>
export default {
  props: ['addMenu'],
  components: {
    name: '',
    price: ''
  }
}
</script>

<style>

</style>
