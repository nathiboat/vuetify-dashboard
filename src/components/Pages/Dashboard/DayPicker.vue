<template>  
    <div>
        <v-slide-group
      v-model="selectedDays"
      class="py-4"
      multiple
       max="2"
      show-arrows
    >
      <v-slide-item
        v-for="day in days"
        :key="day"
        v-slot="{ active, toggle }"
      >
        <v-btn
          class="mx-2"
          :input-value="active"
          active-class="blue white--text"
          depressed
        
          @click="toggle"
        >
          {{day}}
        </v-btn>
      </v-slide-item>
    </v-slide-group>
    </div>
</template>

<script>
    
    export default {
        data: () => ({
           selectedDays: [],
           days: ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', "Sat"]
        }),
        methods:{
         
        }
        
    }
</script>
