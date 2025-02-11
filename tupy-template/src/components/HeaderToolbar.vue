<template>
  <div class="container">
    <v-navigation-drawer v-model="drawer" :rail="rail" permanent>
      <v-list-item :style="listItemStyle" nav>
        <template v-slot:prepend>
          <img :src="Logo" alt="Logo" />
        </template>
      </v-list-item>
      <v-divider></v-divider>
      <v-expansion-panels>
        <v-expansion-panel @click="rail = false">
          <v-expansion-panel-title expand-icon="mdi-chevron-down">
            <v-icon small class="mr-7">mdi-account</v-icon>
            <span class="text-subtitle-2">Usuarios</span>
          </v-expansion-panel-title>
          <v-expansion-panel-text :style="dataToolBar">
            <v-list nav>
              <v-list-item prepend-icon="mdi-home-city" title="Home" value="home"></v-list-item>
              <v-list-item prepend-icon="mdi-home-city" title="Home" value="sub"></v-list-item>
              <v-list-item prepend-icon="mdi-home-city" title="Home" value="tube"></v-list-item>
            </v-list>
          </v-expansion-panel-text>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-navigation-drawer>
  </div>
</template>

<script lang="ts">
import { CSSProperties } from 'vue';
import { Vue, Options } from 'vue-class-component';
import LogoTupy from '../assets/images/LogoTupy.png';

@Options({
    props: {
        rail: Boolean
    }
})
export default class HeaderToolbar extends Vue {
    Logo: string = LogoTupy;
    drawer = true;
    rail = false;

    get listItemStyle(): CSSProperties {
        return {
            width: this.rail ? '90px' : 'auto',
            transition: 'width 0.3s',
            color: '#0f4279'
        };
    }

    get logoStyle(): CSSProperties {
        return {
            height: this.rail ? '75px' : '75px',
            objectFit: 'cover',
            transition: 'width 0.3s'
        };
    }

    get dataToolBar(): CSSProperties {
        return {
            display: this.rail ? 'none' : 'flex'
        };
    }
}
</script>

<style>
.container {
    display: flex;
    flex-direction: column;
    height: 100vh;
}

.header {
    height: 75px; /* Defina a altura desejada para o header */
}

.header-toolbar {
    /*height: 0px;*/ /* Defina a altura desejada para o HeaderToolbar */
    color: #000;
}

.content {
    flex: 1;
    overflow: auto;
    height: calc(100vh - 125px);
}
</style>
