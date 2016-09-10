<template>
  <div id="app">
    <app-header></app-header>
    <menus :menus="menus" :remove-menu="removeMenu"></menus>
    <hr>
    <new-menu :add-menu="addMenu" :on-input="onInput"></new-menu>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader'
import Menus from './components/Menus'
import NewMenu from './components/NewMenu'

export default {
  components: {
    AppHeader,
    Menus,
    NewMenu
  },
  data () {
    return {
      menus: [
        {
          name: 'สุกี้น้ำ'
        },
        {
          name: 'คั่วกลิ้ง'
        }
      ]
    }
  },
  methods: {
    addMenu (name) {
      name = name.trim()
      let isMenuExist = this.menus.find(function (menu) {
        return menu.name === name
      })
      if (name !== '' && !isMenuExist) {
        let newMenu = { name }
        this.menus.push(newMenu)
      }
    },
    removeMenu (index) {
      this.menus.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
