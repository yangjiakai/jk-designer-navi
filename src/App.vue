<template>
  <v-app>

    <v-toolbar app dark clipped-left color="rgb(28,32,33)">
      <v-toolbar-title class="headline">
        <v-icon color="rgb(49,193,147)">track_changes</v-icon>
        设计导航
      </v-toolbar-title>
      <v-toolbar-side-icon  @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-items>
        <v-btn color="rgb(49,193,147)" to="/ui"  flat>
            <v-icon>near_me</v-icon>
            Web/UI
        </v-btn>
        <v-btn color="rgb(49,193,147)" to="/architecture" flat>
            <v-icon>select_all</v-icon>
            建筑/室内
        </v-btn>
        <v-btn color="rgb(49,193,147)" to="/book" flat>
            <v-icon>library_books</v-icon>
            设计书籍
        </v-btn>
      </v-toolbar-items>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat to="/"><v-icon>turned_in</v-icon></v-btn>
        <v-btn flat to="/about"><v-icon>view_column</v-icon></v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer app v-model="drawer" clipped dark width="220px" permanent>
      <SideMenu />
    </v-navigation-drawer>
    <v-content class="content-area">
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
  import SideMenu from './components/SideMenu'
  export default {
    name: 'App',
    components: {
      SideMenu
    },
    data() {
      return {
        // 侧边栏
        drawer: null
      }
    }
  }
</script>

<style lang="stylus" scoped>


.card 
  height 1000px 

.content-area
  background-color rgb(231,239,244)
  
</style>