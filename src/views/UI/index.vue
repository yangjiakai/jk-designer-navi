<template>
  <v-container grid-list-md>
    <template v-for="card in cards">
      <v-card class="main-card">
        <v-card-title class="main-title">
          <v-icon color="rgb(81,129,147)" class="mx-2">layers</v-icon>
          {{card.card_title}}
          <a class="main-describe" :src="card.card_subtitle_url">{{card.card_subtitle}}</a>
        </v-card-title>
        <v-divider></v-divider>
        <v-layout my-2>
          <template v-for="type in card.site_types">
            <v-flex xs2 class="sub-title">
              {{type.type_name}}
            </v-flex>
            <v-flex xs10 mr-2>
              <v-layout row wrap>
                <v-flex xs2 v-for="site in type.sites">
                  <v-card hover class="sub-card" flat>
                    <v-card-text primary-title class="sub-card-title">
                      {{site.site_name}}
                    </v-card-text>
                    <v-card-text class="sub-card-text">
                      {{site.site_descripse}}
                    </v-card-text>
                  </v-card>
                </v-flex>
              </v-layout>
            </v-flex>
          </template>

        </v-layout>
        <v-divider></v-divider>
      </v-card>
      <v-divider class="my-5"></v-divider>
    </template>
    <v-layout row wrap>
      <v-btn color="success">
        UI
      </v-btn>
    </v-layout>
  </v-container>
</template>

<script>
  import axios from 'axios'
  import {log} from 'util';
  import {async} from 'q';
  export default {
    data() {
      return {
        cards: []
      }
    },
    methods: {

    },
    mounted() {

    },
    computed: {

    },
    created() {
      this.$nextTick(() => {
        axios.get('http://localhost:3000/cards')
          .then(res => {
            console.log(res);
            console.log(res.data);

            this.cards = res.data
            console.log(this.cards);
          })


      })


    }
  }
</script>

<style lang="stylus" scoped>
  .main-card 
    border-radius 10px
    .main-title 
      color:rgb(81,129,147)
      .main-describe
        color:#f46c0e
        margin 0 30px
        &:hover
          color:#0065a9
  
  .sub-title
    text-indent:30px
    margin-top 15px
    font-size 15px
    color #ccc

  .sub-card
    .sub-card-title
      color #00ad35
    .sub-card-text
      color #a2a8a2
    &:hover
      background-color:rgb(237,245,250)
      .sub-card-title,.sub-card-text
        color rgb(0,101,169)

</style>