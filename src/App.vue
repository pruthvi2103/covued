<template>
<div id="app" :class="(mode === 'dark') ? 'dark' : ' '">
 
<Header :mode="mode" :updated="popoverdat"></Header>
  <div  class="container">
  
  <div class="row">
    <div class="col-md-8 offset-md-2">
     <Title></Title>
      <IndiaCounter :indiaData="indInfo.total"></IndiaCounter>
      
      
    </div>
    </div>
    <div class="row">
    <div class="col-md-8 offset-md-2">
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
import StateCounter from './components/StateCounter';
import Header from './components/Header'

  export default {
    name:'app',
    components:{
                  IndiaCounter,Title,StateCounter,Header
    },
    data(){
      return { 
      indInfo: [ {} ],
      popoverdat: '',
      mode: 'dark'
      
      };
    },
    methods:{
      
       
         },
    computed:{
popoverData() {
        
        return {
          title: 'Information',
          content: 'Last Updated: ' + this.popoverdat.substring(0,this.popoverdat.indexOf("T"))
        }
      }
    },
    mounted () {
    axios
      .get('https://api.rootnet.in/covid19-in/unofficial/covid19india.org/statewise.json')
      .then(response => (this.indInfo = response.data.data).then(this.popoverdat = this.indInfo.lastRefreshed));
      
    
  }
  }
</script>

<style lang="css" scoped>

*{
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  
}

.dark{
  background-color: #192734;
  color: #f3f3f3;
}
.popover-header{
  background-color: white !important;
}




</style>