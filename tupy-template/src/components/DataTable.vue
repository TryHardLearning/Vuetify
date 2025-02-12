<template>
  <v-container fluid class="d-flex flex-column" style="flex: 1; padding: 30px;">
    <v-row>
      <v-col cols="4" md="4">
        <v-text-field clearable label="Pesquisar"></v-text-field>
      </v-col>
      <v-col cols="4" md="4">
        <v-date-input clearable label="Data da Ocorencia" variant="outlined"></v-date-input>
      </v-col>
      <v-col cols="4">
        <v-combobox multiple label="Local"
          :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"></v-combobox>
      </v-col>
    </v-row>
    <v-row justify="end">
      <v-col cols="auto">
        <v-btn prepend-icon="mdi-magnify" color="green">
          Search
        </v-btn>
      </v-col>
      <v-col cols="auto">
        <v-btn prepend-icon="mdi-content-save-outline" color="blue">
          Novo Cadastro
        </v-btn>
      </v-col>
    </v-row>
    <v-row class="d-flex align-center justify-center" style="flex: 1; box-shadow: 2px 2px 6px #a9a9a9; margin-top: 30px;">
      <v-col cols="12" style="">
        <v-divider></v-divider>
        <v-data-table-virtual :headers="headers" :items="virtualBoats" height="42vh" width="auto"
          item-value="name"></v-data-table-virtual>
        <v-divider></v-divider>
        <v-pagination :length="4"></v-pagination>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import '@mdi/font/css/materialdesignicons.css';

interface Header {
  title: string;
  align?: 'start' | 'end' | 'center';
  key: string;
}

@Options({
  name: 'DataTable'
})
export default class DataTable extends Vue {
  headers: Header[] = [
    { title: 'Boat Type', align: 'start', key: 'name' },
    { title: 'Speed (knots)', align: 'end', key: 'speed' },
    { title: 'Length (m)', align: 'end', key: 'length' },
    { title: 'Price ($)', align: 'end', key: 'price' },
    { title: 'Year', align: 'end', key: 'year' }
  ];

  boats = [
    { name: 'Speedster', speed: 35, length: 22, price: 300000, year: 2021 },
    { name: 'OceanMaster', speed: 25, length: 35, price: 500000, year: 2020 },
    { name: 'Voyager', speed: 20, length: 45, price: 700000, year: 2019 },
    { name: 'WaveRunner', speed: 40, length: 19, price: 250000, year: 2022 },
    { name: 'SeaBreeze', speed: 28, length: 31, price: 450000, year: 2018 },
    { name: 'HarborGuard', speed: 18, length: 50, price: 800000, year: 2017 },
    { name: 'SlickFin', speed: 33, length: 24, price: 350000, year: 2021 },
    { name: 'StormBreaker', speed: 22, length: 38, price: 600000, year: 2020 },
    { name: 'WindSail', speed: 15, length: 55, price: 900000, year: 2019 },
    { name: 'FastTide', speed: 37, length: 20, price: 280000, year: 2022 }
  ];

  get virtualBoats() {
    return [...Array(100).keys()].map(i => {
      const boat = { ...this.boats[i % this.boats.length] };
      boat.name = `${boat.name} #${i}`;
      return boat;
    });
  }
}
</script>

<style scoped></style>