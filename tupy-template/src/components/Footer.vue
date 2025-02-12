<template>
    <v-container fluid>
      <v-footer border
        style="
          justify-content: space-between;
          font-size: small;
          font-weight: 400;
          font-family: Roboto;
          color: #757575;
        "
        ><label>Tupy S.A</label><label><v-icon>mdi-copyright</v-icon>Todos os diretos reservados</label>
      </v-footer>
    </v-container>
</template>

<script lang="ts">
import { Vue, Options } from 'vue-class-component';

@Options({
  props: {
  }
})
export default class Footer extends Vue {

}
</script>