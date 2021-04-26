<template>
  <v-app>
    <v-system-bar app>
      <h2>Report</h2>
      <v-spacer></v-spacer>
      <v-icon>mdi-square</v-icon>
      <v-icon>mdi-circle</v-icon>
      <v-icon>mdi-triangle</v-icon>
    </v-system-bar>
    <v-app-bar
      app
      color="white"
    >
        <v-responsive >
          <v-text-field
            prepend-icon="mdi-search-web"
            dense
            hide-details
            filled
          ></v-text-field>
        </v-responsive>
    </v-app-bar>   
   
    <v-main class="grey lighten-3">
      <v-container>
        <v-row no-gutters>
          <v-col cols="1">
            <v-sheet >
              <SidebarList/>
            </v-sheet>
          </v-col>

          <v-col cols="6">
            <v-sheet>
              <Dashboard/>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Dashboard from './components/Pages/Dashboard';
import SidebarList from './components/Sidebar/List';


export default {
  name: 'App',

  components: {
    Dashboard,
    SidebarList
  },

  data: () => ({
  }),
};
</script>
