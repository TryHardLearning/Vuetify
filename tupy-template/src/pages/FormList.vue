<template>
  <v-app>
    <v-main fluid>
      <Header :rail="rail" />
      <div style="display: flex; flex-direction: row; justify-content: space-between;" >
        <HeaderToolbar :rail="rail" :class="{ 'toolbar-expanded': !rail, 'toolbar-collapsed': rail }" />
        <DataTable />
      </div>
      <Footer />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Header from '@/components/Header.vue';
import HeaderToolbar from '@/components/HeaderToolbar.vue';
import DataTable from '@/components/DataTable.vue';
import Footer from '@/components/Footer.vue';

@Options({
  name: 'FormList',
  components: {
    Header,
    HeaderToolbar,
    DataTable,
    Footer
  }
})
export default class FormList extends Vue {
  rail = false;

}
</script>

<style scoped>
.toolbar-expanded {
  height: 50px; /* Altura desejada para HeaderToolbar expandido */
  transition: height 0.3s;
}

.toolbar-collapsed {
  height: 25px; /* Altura desejada para HeaderToolbar reduzido */
  transition: height 0.3s;
}

.data-table {
  flex: 1;
  overflow-y: auto;
}
</style>
