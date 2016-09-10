<template>
  <div>
    <div class="">
      <form @submit.prevent="addAndClearInputMenu()">
        <input v-model="inputMenu">
        <input type="submit" value="Add(By submit)">
      </form>
    </div>
    <hr>
    <div class="">
      <input v-model="inputMenu" @keydown.enter="addAndClearInputMenu()">
      <button @click="addAndClearInputMenu()">Add(By Enter)</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['addMenu'],
  data () {
    return {
      inputMenu: ''
    }
  },
  methods: {
    addAndClearInputMenu: function () {
      this.addMenu(this.inputMenu)
      this.inputMenu = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
