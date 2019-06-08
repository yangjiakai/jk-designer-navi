<template>
  <v-list dense>
    <v-list-group
      v-model="value"
      v-for="item in items"
      :key="key"
      :prepend-icon="icon"
      no-action
    >
    </v-list-group>
    <v-list-tile avatar v-for="i in 9" @click="">
      <v-list-tile-avatar>
        <v-icon color="rgb(112,137,133)">room</v-icon>
      </v-list-tile-avatar>
      <v-list-tile-content>
        <v-list-tile-title>设计素材</v-list-tile-title>
      </v-list-tile-content>
      <v-btn icon ripple>
        <v-icon color="grey lighten-1">control_camera</v-icon>
      </v-btn>
    </v-list-tile>
    <v-divider></v-divider>
    <v-subheader>以下Tab请点+号展开</v-subheader>
    <v-list-tile avatar v-for="i in 8" @click="">
      <v-list-tile-avatar>
        <v-icon color="rgb(112,137,133)">room</v-icon>
      </v-list-tile-avatar>
      <v-list-tile-content>
        <v-list-tile-title class="memu">设计素材</v-list-tile-title>
      </v-list-tile-content>
      <v-btn icon ripple>
        <v-icon color="grey lighten-1">control_camera</v-icon>
      </v-btn>
    </v-list-tile>
  </v-list>
</template>

<script>
  import VuePerfectScrollbar from 'vue-perfect-scrollbar'
  export default {
    data() {
      return {

      }
    },
    methods: {


    },
    components: {
      VuePerfectScrollbar
    }
  }
</script>

<style scoped lang="stylus">
</style>