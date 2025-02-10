<template>
    <v-app>
        <v-card style="height: 100vh;">
            <v-layout style="height: 100%;">
                <v-navigation-drawer v-model="drawer" :rail="rail" permanent style="min-width: 75px;">
                    <v-list-item :style="listItemStyle" style="display: flex; justify-content: center;" nav
                        height="75px">
                        <template v-slot:prepend>
                            <img src="../assets/LogoTupy.png" alt="Logo" :style="logoStyle" />
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
                        <v-expansion-panel @click="rail = false">
                            <v-expansion-panel-title expand-icon="mdi-chevron-down">
                                <v-icon small class="mr-7">mdi-cog-outline</v-icon>
                                <span class="text-subtitle-2">Software</span>
                            </v-expansion-panel-title>
                            <v-expansion-panel-text :style="dataToolBar">
                                <v-list>
                                    <v-list-item>Item 1.1</v-list-item>
                                    <v-list-item>Item 1.2</v-list-item>
                                    <v-list-item>Item 1.3</v-list-item>
                                </v-list>
                            </v-expansion-panel-text>
                        </v-expansion-panel>
                    </v-expansion-panels>

                </v-navigation-drawer>
                <v-main height="75px">
                    <v-card style="padding: 0 25px" color="#305b97" height="75px" rounded="0" flat>
                        <v-toolbar extended color="#305b97" class="d-flex align-items-center">
                            <v-btn icon="mdi-chevron-left" variant="text" @click.stop="rail = !rail" class="flex-grow-0"
                                :style="{ zIndex: 10 }"></v-btn>
                            <v-toolbar-title class="flex-grow-1">Tipo Cadastro</v-toolbar-title>
                            <v-spacer></v-spacer>
                            <v-btn icon class="flex-grow-0">
                                <v-badge color="error" content="2">
                                    <v-icon>mdi-bell-outline</v-icon>
                                </v-badge>
                            </v-btn>
                            <v-btn icon class="flex-grow-0">
                                <v-icon>mdi-cog-outline</v-icon>
                            </v-btn>
                        </v-toolbar>
                    </v-card>
                </v-main>
            </v-layout>
        </v-card>
    </v-app>
</template>

<script lang="ts">
import { CSSProperties } from 'vue';
import { Vue, Options } from 'vue-class-component';

@Options({
    props: {
        msg: String
    }
})
export default class Header extends Vue {
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