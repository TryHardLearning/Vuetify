<template>
  <Header />
  <DataTable />
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Header from './Header.vue';
import DataTable from './DataTable.vue';

@Options({
  props: {
    msg: String
  }
})
export default class FormList extends Vue {
  msg!: string
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
