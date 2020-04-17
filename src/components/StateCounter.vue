<template>
  <li class="list-group-item">
      <h4>{{ state.state }}</h4>
        <div class="row">
         <div class="col-md-3">
             
             <div class="alert alert-primary">
                 <h6 class="alert-heading"> {{ state.confirmed }}
                 </h6>
                 <p>Confirmed Cases</p>
             </div>
             </div> 

                 <div class="col-md-3">
             <div class="alert alert-success">
                 <h6 class="alert-heading">{{ state.recovered }}
                 </h6>
                 <p>Recovered Cases</p>
             </div>
             </div> 
             

                 <div class="col-md-3">
             <div class="alert alert-danger">
                 <h6 class="alert-heading">{{ state.deaths }}
                 </h6>
                 <p>Deaths</p>
             </div>
             </div> 

                 <div class="col-md-3">
             <div class="alert alert-warning">
                 <h6 class="alert-heading">{{ state.active }}
                 </h6>
                 <p>Active Cases</p>
             </div>
             </div> 
        </div>

  </li>
</template>

<script>
export default {
props: ['state']
}
</script>

<style scoped>

.col-md-3{
    padding: 0px;
}
.alert{
    margin: 5px;
    padding: 5px;
}

.col-md-6{
    padding: 0px;
}

p,.alert-heading{
    margin: 4px;
    padding-left: 10px;
}

</style>>

