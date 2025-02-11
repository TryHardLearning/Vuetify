<template>
  <v-app>
    <v-container fluid style="height: 100vh;">
      <v-row no-gutters>
        <v-col cols="12" width="100vw">
          <Header />
        </v-col>
        <v-col cols="12" class="d-flex flex-column" style="overflow: auto; padding-top: 75px;">
          <DataTable />
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Header from './Header.vue';
import DataTable from './DataTable.vue';

@Options({
  name: 'FormList',
  components: {
    Header,
    DataTable
  }
})
export default class FormList extends Vue {}
</script>

<style scoped>
.v-container {
  display: flex;
  flex-direction: column;
}
.v-col {
  display: flex;
  flex-direction: column;
  flex: 1;
}
</style>
