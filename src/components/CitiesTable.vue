<template>

        <div v-if="loaderShow" class="w-100 text-center pt-5">
            <img src="../assets/loader.gif" alt="" style="height: 100px;width: 120px">
        </div>
        <b-table v-else striped hover :items="items" :fields="fields"></b-table>

</template>

<script>

    import axios from 'axios';

    export default {
        name: "CitiesTable",
        data() {
            return {
                loaderShow:true,
                fields: ['name', 'latitude', 'longitude'],
                items:[]
            }
        },
        methods:{
            getCities(){
                axios.get('http://localhost:8000/get-city')
                    .then(data=>{
                        this.items=data.data
                        this.loaderShow=false
                })
            }
        },
        created() {
            this.getCities();
        }
    }
</script>

<style scoped>

</style>