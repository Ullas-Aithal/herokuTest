<template>
<v-container fluid grid-list-md text-xs-center>
            <v-layout row>
    <v-flex>
        <v-card>
            <v-card-title>
                <h1>{{currentTime}}</h1>
            </v-card-title>        
        </v-card>
    </v-flex>
</v-layout> 
</v-container>
</template>
<script>
import moment from 'moment'
export default {
    name:'Header',
    data(){
        return{
            heading:'Weather',
            datenow: '',
            moment: moment,
            currentTime: null
        }
    },
    methods: {
    updateCurrentTime() {
      this.currentTime = moment().format('LTS');
    }
  },
  created() {
    this.currentTime = moment().format('LTS');
    setInterval(() => this.updateCurrentTime(), 1 * 1000);
  }
}
</script>
