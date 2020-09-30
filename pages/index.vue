<template lang="html">
  <div>
    <v-tabs
      fixed-tabs
      background-color="red"
    >
      <v-tab>
        I AM NASA
      </v-tab>
    </v-tabs>
    <v-text-field v-model="query" label="โปรดใส่ข้อความที่คุณอยากรู้เกี่ยวกับ NASA (กรุณาใส่เป็นภาษาอังกฤษ)" />
    <v-btn large color="green accent-3" @click="SearchNasa">
      ค้นหา
    </v-btn>
    <v-progress-circular
      indeterminate
      color="primary"
    />
    <v-progress-circular
      indeterminate
      color="red"
    />
    <v-progress-circular
      indeterminate
      color="purple"
    />
    <v-progress-circular
      indeterminate
      color="green"
    />
    <v-progress-circular
      indeterminate
      color="amber"
    />
    <v-row justify="center">
      <v-card
        v-for="list in nasa"
        :key="list.items"
        width="344"
        class="mx-auto"
        src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
      >
        <nuxt-link :to=" {name: 'product-id', params: { id: list }} ">
          <v-img :src="list.links[0].href" height="194" />
        </nuxt-link>
      </v-card>
    </v-row>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      query: '',
      nasa: ''
    }
  },
  methods: {
    SearchNasa () {
      const url = 'https://images-api.nasa.gov/search?q=' + this.query + ''
      axios.get(url).then((response) => {
        this.nasa = response.data.collection.items.slice(1, 13)
      })
    }
  }
}
</script>
