<template>
        <div>
                <div v-if="loaderShow" class="w-100 text-center pt-5" >
                        <img src="../assets/loader.gif" alt="" style="height: 100px;width: 120px">
                </div>
                <b-table v-else ref="table" striped hover :items="items" :fields="fields"></b-table>
                <div v-if="showError" class="text-center pb-5 pt-5 bg-danger">
                        Something went wrong
                </div>
        </div>


</template>

<script>

    export default {
        name: "WeatherTable",
        data (){
           return {
                loaderShow:true,
                showError:false,
                fields: ['time','name', 'latitude', 'longitude','temp','pressure','humidity','temp_min','temp_max'],
                items: []
            }
        },
        mounted() {
                 window.Echo.channel('channel')
                     .listen('Weather',(e)=>{
                             this.showError=false
                             this.loaderShow=false
                             if(e.cod==200){
                                      this.items=e.data
                             }else{
                                     this.showError=true
                             }
                     })
            }
    }
</script>

<style scoped>

</style>