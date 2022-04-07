<template>
    <div>
        <div class="courses-container" v-for="record in vinyls" :key="record.id">
            <h1>Découvrez nos vinyls</h1>
            <div class="course">
                <div class="course-preview" :style="{ backgroundColor: cardColor }">
                    <slot>
                        <h2>En stock</h2>
                        <img class="main-image" :src="record.picture_link" height="200px" href="#" />
                    </slot>
                </div>
                <div class="course-info">
                    <h6>{{ record.band }}</h6>
                    <h2>Titre du vinyls{{ record.title }}</h2>

                    <button class="btn" @click="selectCourse" href="#VinylsDetails.html">Voir</button>
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
    }
}


</script>


<style scoped>
@import "../assets/static/css/vinyl_list.css";
</style>