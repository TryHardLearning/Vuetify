<template>
  <v-app>
    <v-main>
      <FormEdit />
    </v-main>
  </v-app>
  
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import DataTable from '@/components/DataTable.vue'
import FormList from '@/pages/FormList.vue';
import FormEdit from '@/pages/FormEdit.vue';

export default defineComponent({
  name: 'App',

  components: {
    FormEdit
  },

  data () {
    return {
      //
    }
  },
})
</script>
