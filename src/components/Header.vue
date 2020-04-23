<template>
    <header>
         <hr />
    <div class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Covued</a>
      <ul class="navbar-nav ml-auto">
        <li class="nav-item">
          <i class="fa fa-moon-o" aria-hidden="true"></i>
        </li>
            <li class="nav-item">
                <i v-b-popover.bottomleft="popoverData" class="fa fa-info-circle fa-lg" aria-hidden="true"></i>
            
            </li>

        </ul>
      

    </div>
    </header>
</template>

<script>
    export default {
        data() {
            return {

            }
        },
        props : ['mode','updated'],
        computed:{
                    popoverData() {
        
        return {
          title: 'Information',
          content: 'Last Updated: ' + this.updated.substring(0,this.updated.indexOf("T"))
        }
      }
        }
    }
</script>

<style lang="css" scoped>
i{
  padding: 5px;
  margin: 10px;
}

.navbar{
  padding-bottom: 5px;
  padding-top: 5px;
  margin-bottom: 10px;
}
hr{
  border: 5px solid #6200EE;
  margin-bottom: 0px;
  padding-top: -10px;
  margin-top: 0px;
}

</style>