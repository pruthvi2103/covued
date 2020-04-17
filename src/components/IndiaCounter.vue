<template>
    <div>
<h3>Total Stastics</h3>
        <div class="row">
         <div class="col-md-6">
             <div class="alert alert-primary">
                 <h6 class="alert-heading"> {{ indiaData.confirmed }}
                 </h6>
                 <p>Confirmed Cases</p>
             </div>
             </div> 

                 <div class="col-md-6">
             <div class="alert alert-success">
                 <h6 class="alert-heading">{{ indiaData.recovered }}
                 </h6>
                 <p>Recovered Cases</p>
             </div>
             </div> 
             </div>
<div class="row">
                 <div class="col-md-6">
             <div class="alert alert-danger">
                 <h6 class="alert-heading">{{ indiaData.deaths }}
                 </h6>
                 <p>Deaths</p>
             </div>
             </div> 

                 <div class="col-md-6">
             <div class="alert alert-warning">
                 <h6 class="alert-heading">{{ indiaData.active }}
                 </h6>
                 <p>Active Cases</p>
             </div>
             </div> 
</div>
<div class="row">
    <div class="col">
    <div class="alert alert-dark"><p>Made By: Pruthvi Shetty.</p></div>
    </div>
</div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                
            };
        },
        props: ['indiaData'],
        mounted(){
            
        }
        
    }
</script>

<style lang="css" scoped>

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



</style>