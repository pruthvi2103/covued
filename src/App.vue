<template>
<div>
  <hr />
  <div id="app" class="container">
  <div class="row">
    <div class="col-md-4">
     <Title></Title>
      <IndiaCounter :indiaData="indInfo.total"></IndiaCounter>
      
    </div>
    <div class="col-md-8">
      <ul class="list-group">
      <StateCounter 
      v-for="states in indInfo.statewise"
      :state="states"
      :key="states.state"> </StateCounter>
      </ul>
    </div>
  
 

  </div>
  </div>
  </div>
</template>

<script>
import axios from 'axios';
import IndiaCounter from './components/IndiaCounter';
import Title from './components/Title';
import StateCounter from './components/StateCounter'
  export default {
    name:'app',
    components:{
                  IndiaCounter,Title,StateCounter
    },
    data(){
      return { 
      indInfo: [ {} ]
      };
    },
    methods:{
       
         },
           

         
        
       
       
    mounted () {
    axios
      .get('https://api.rootnet.in/covid19-in/unofficial/covid19india.org/statewise.json')
      .then(response => (this.indInfo = response.data.data))
  }
  }
</script>

<style lang="css" scoped>

hr{
  border: 5px solid #6200EE;
  margin-bottom: 10px;
  padding-top: -10px;
}

</style>