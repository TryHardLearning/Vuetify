<template>
  <div class="home">
    <Header />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import FormList from '@/components/FormList.vue';
import Header from '@/components/Header.vue';

@Options({
  components: {
    Header,
  },
})
export default class HomeView extends Vue {}
</script>
