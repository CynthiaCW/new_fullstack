<template>
    <div>
        <div class="courses-container">
            <h1>Découvrez nos vinyls</h1>
            <div class="course" v-for="record in vinyls" :key="record.id">
                <div class="course-preview">
                    <slot>
                        <h2 style="color:black">{{(record.available==1)?'✔':'❌'}}</h2>
                        <img class="main-image" :src="record.picture_link" height="200px" href="#" />
                    </slot>
                </div>
                <div class="course-info" >
                    
                    <h6>{{ record.band }}</h6>
                    <h2>{{ record.title }}</h2>

                    <button class="btn" @click="showVinylDetails(record.id)">Voir</button>
                </div>
            </div>
        </div>
    </div>
</template>



<script>
import axios from 'axios'
const API = 'http://localhost:8000/read.php'

export default {
    name: 'ListVue',
    data: () => ({
        vinyls: []
    }),
    async created() {
        const vinyls = await axios.get(API)
        this.vinyls = vinyls.data
    },
    methods:{
        showVinylDetails(recordId){
            this.$router.push({name:'recordDetails', params:{recordId: recordId}})
        }
    }
}


</script>


<style scoped>
@import "../assets/static/css/vinyl_list.css";
</style>
