<template>
  <v-app>
    <v-main>
      <FormList />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import DataTable from '@/components/DataTable.vue'
import FormList from '@/components/FormList.vue';

export default defineComponent({
  name: 'App',

  components: {
    FormList,
  },

  data () {
    return {
      //
    }
  },
})
</script>
