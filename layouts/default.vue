<template>
  <v-app dark>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'I AM NASA'
    }
  }
}
</script>
<style>
.theme--dark.v-application{
  background-image:url('https://media4.giphy.com/media/l44QEb8dHxDUucEYo/giphy.gif?cid=ecf05e47f1ab3a6655586c09ac39295920ee388bd47cfd4e&rid=giphy.gif') ;
  background-size: 1300px;

}
</style>
