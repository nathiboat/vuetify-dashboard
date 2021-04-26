<template>
  <v-container>
    <v-row class="mx-4 my-4">
        <h4>SCHEDULING</h4>
    </v-row> 
    <Steps/>   
    <v-row  class="mx-4 my-4">
        <v-col>
             <v-card
    class="mx-auto"
    
    outlined
  >
    <v-list-item three-line>
        
      <v-list-item-avatar
        tile
        size="80"
        color="grey"
      ></v-list-item-avatar>
      <v-list-item-content>
        <div class="overline mb-4">
          OVERLINE
        </div>
        <v-list-item-title class="headline mb-1">
          Headline 5
        </v-list-item-title>
        <v-list-item-subtitle>Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle>
      </v-list-item-content>

    </v-list-item>
  </v-card>
        </v-col>
    </v-row>
    <v-row  class="mx-4 my-4">
        <v-col>
            <v-divider></v-divider>
            <div class="my-4">
                 <h4 >A. Scheduled Report Name</h4>
            </div>
           
            <v-divider></v-divider>

            <div class="my-4">
                
                <v-text-field
                    label="Outlined"
                    placeholder="Placeholder"
                    outlined
                    dense
                ></v-text-field>
                <v-alert
                    dense
                    border="left"
                    type="warning"
                    >
                    A unique report name is required to easily identify the scheduled report.
                </v-alert>
            </div>
        </v-col>
    </v-row>

    <v-row  class="mx-4 my-4">
        <v-col>
            <v-divider></v-divider>
            <div class="my-4">
                 <h4 >B. Report Recurrence</h4>
            </div>

            <v-divider></v-divider>

            <div class="my-4">
                <p>Report Recurrence</p>
                <v-select
                    :items="plan"
                  
                    outlined
                ></v-select>

                <p>Report will run every week on the following days.</p>
                <DayPicker/>

                <p>Start Date $ Time</p>
                <v-menu
                    ref="menu"
                    v-model="menu"
                    :close-on-content-click="false"
                    :return-value.sync="date"
                    transition="scale-transition"
                    offset-y
                    min-width="auto"
                >
                    <v-text-field
                        v-model="date"
                        label="Picker in menu"
                        prepend-icon="mdi-calendar"
                        readonly
                        v-bind="attrs"
                        v-on="on"
                    ></v-text-field>
                </v-menu>    
                <p>End Date $ Time</p>
            
            
            </div>
        </v-col>
    </v-row>
  </v-container>
</template>

<script>
    import Steps from './Dashboard/Steps'
    import DayPicker from './Dashboard/DayPicker'

    export default {
        components: {
            Steps,
            DayPicker
        },
        name: 'Dashboard',

        data: () => ({
            plan: ['Weekly'],
            date: new Date().toISOString().substr(0, 10),
            menu: false,
            modal: false,
            menu2: false,
    
        }),
    }
</script>
