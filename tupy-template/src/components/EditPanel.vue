<template>
    <v-container fluid class="d-flex flex-column" style="flex: 1; padding: 30px;">
        <v-toolbar-title style="margin-bottom: 25px; font-size: 1.2rem;"><v-icon>mdi-cog-outline</v-icon> Tipo
            Cadastro</v-toolbar-title>
        <v-row>
            <v-col cols="4" md="4">
                <v-text-field clearable label="Codigo do Produto"></v-text-field>
            </v-col>
            <v-col cols="4" md="4">
                <v-date-input clearable label="Data da Ocorencia" variant="outlined"></v-date-input>
            </v-col>
            <v-col cols="4">
                <v-combobox multiple label="Local"
                    :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"></v-combobox>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="4" md="4">
                <v-text-field clearable label="Nome do Produto"></v-text-field>
            </v-col>
            <v-col cols="4" md="4">
                <v-text-field clearable label="Responsavel"></v-text-field>
            </v-col>
        </v-row>
        <v-row justify="end">
            <v-col cols="auto">
                <v-btn prepend-icon="mdi-content-save-outline" color="blue">
                    Salvar
                </v-btn>
            </v-col>
            <v-col cols="auto">
                <v-btn prepend-icon="mdi-close" color="red">
                    Cancelar
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
    name: 'EditPanel',
    components: {

    }
})
export default class EditPanel extends Vue {
}
</script>

<style></style>