<template>
  <div>
    Picture :{{ this.$route.params.id.links[0].href }} <br><br>
    Title : {{ this.$route.params.id.data[0].title }} <br><br>
    description:{{ this.$route.params.id.data[0].description }} <br><br>
  </div>
</template>
