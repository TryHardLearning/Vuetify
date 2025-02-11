<template>
    <v-app>
      <v-card>
        <v-layout>
          <v-navigation-drawer v-model="drawer" :rail="rail" permanent>
            <v-list-item :style="listItemStyle" nav>
              <template v-slot:prepend>
                <img :src="Logo" alt="Logo" />
              </template>
            </v-list-item>
            <v-divider></v-divider>
            <v-expansion-panels>
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
            </v-expansion-panels>
          </v-navigation-drawer>
          <v-main>
            <v-toolbar color="#305b97">
              <v-btn icon="mdi-chevron-left" @click.stop="rail = !rail"></v-btn>
              <v-toolbar-title>Tipo Cadastro</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-badge color="error" content="2">
                  <v-icon>mdi-bell-outline</v-icon>
                </v-badge>
              </v-btn>
              <v-btn icon>
                <v-icon>mdi-cog-outline</v-icon>
              </v-btn>
            </v-toolbar>
          </v-main>
        </v-layout>
      </v-card>
    </v-app>
  </template>

<script lang="ts">
import { CSSProperties } from 'vue';
import { Vue, Options } from 'vue-class-component';
import LogoTupy from '../assets/images/LogoTupy.png';

@Options({
    props: {
        msg: String
    }
})
export default class Header extends Vue {
    Logo: string = LogoTupy;
    drawer = true;
    rail = false;
    menuTogle = false;

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

    bars = [
        { class: 'primary', dark: true }
    ];
}
</script>

<style></style>