<template>
    <v-list class="grey lighten-3"  outlined>
        <v-list-item-group
        v-model="selectedItem"
        color="primary"
        >
            <v-list-item
                v-for="link in links"
                :key="link.title"
                link
            >
                <v-list-item-content >
                <v-icon>mdi-{{ link.icon }}</v-icon>
                <v-list-item-title class="text-center">
                    {{ link.title }}
                </v-list-item-title>
                <v-divider></v-divider>

                </v-list-item-content>
            </v-list-item>
        </v-list-item-group>
    </v-list>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
        selectedItem: "",
        links: [
            { title:'DASHBOARD', icon:'monitor-dashboard'},
            { title:'REPORT', icon:'chart-bar'},
            { title:'SCHEDULING', icon:'clock-outline'},
            { title:'SETINGS', icon:'cog-outline'},
        ],
 
    }),
  }
</script>