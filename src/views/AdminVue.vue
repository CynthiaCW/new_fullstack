<template>
    <div>
        <NavBar />

        <div class="courses-container">
            <h1>Découvrez nos vinyls</h1>
            <button class="btn" methods="GET" href>Ajouter un vinyl</button>
            <div class="course" v-for="record in vinyls" :key="record.id">
                <div class="course-preview">
                    <slot>
                        <h2>{{ (record.available == 1) ? '✔' : '❌' }}</h2>
                        <img class="main-image" :src="record.picture_link" height="200px" href="#" />
                    </slot>
                </div>
                <div class="course-info">
                    <h6>{{ record.band }}</h6>
                    <h6>{{ record.year_release }}</h6>
                    <h6>{{ record.genre }}</h6>
                    <h2>{{ record.title }}</h2>

                    <p>{{ record.description }}</p>
                </div>
                <button class="btn" methods="PUT" href>Modifier un vinyl</button>
                <button class="btn" methods="DELETE" href>Supprimer un vinyl</button>
            </div>
        </div>
    </div>
</template>


<script>
import axios from 'axios'
import NavBar from "@/components/NavBar.vue";
const API = 'http://localhost:8000/read.php'

export default {
    name: 'AdminVue',
    components: {
        NavBar
    },
    data: () => ({
        vinyls: []
    }),
    async created() {
        const vinyls = await axios.get(API);
        this.vinyls = vinyls.data;
    }





}

</script>