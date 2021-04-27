<template>
  <div>
    <v-row>
      <v-col cols="12" sm="6" md="4">
        <v-menu          v-model="menu1"
          :close-on-content-click="false"
          :nudge-right="40"
          transition="scale-transition"
          offset-y
          min-width="auto"
        >
          <template v-slot:activator="{ on, attrs }">
            <v-text-field
              v-model="startDate"
              append-icon="mdi-calendar"
              readonly
              v-bind="attrs"
              v-on="on"
            ></v-text-field>
          </template>
          <v-date-picker v-model="startDate" @input="menu1 = false"></v-date-picker>
        </v-menu>
      </v-col>
      <v-spacer></v-spacer>
      <v-col cols="12" sm="6" md="2">
        <v-select
          :items="items"
          dense
          outlined
        ></v-select>
      </v-col>
      <v-col cols="12" sm="6" md="2">
        <v-select
          :items="items"
          
          dense
          outlined
        ></v-select>
      </v-col>
      <v-col cols="12" sm="6" md="3">
        <v-slide-group
          v-model="selectedDays"
          class="py-4"
          show-arrows
        >
          <v-slide-item
            v-for="item in ampm"
            :key="item"
            v-slot="{ active, toggle }"
          >
            <v-btn
              class="mx-2"
              :input-value="active"
              active-class="blue white--text"
              depressed
              @click="toggle"
            >
              {{ item }}
            </v-btn>
          </v-slide-item>
        </v-slide-group>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    startDate: new Date().toISOString().substr(0, 10),
    selectedDays: "",
    items: ['1', '2', '3', '4'],
    menu: false,
    modal: false,
    menu1: false,
    menu2: false,
    ampm: ["AM", "PM"]
  }),
};
</script>