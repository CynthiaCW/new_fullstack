<template>
    <div>
        <NavBar />

        <div class="courses-container">
            <h1>Découvrez nos vinyls</h1>
            <button class="btn" methods="PUT" @click="createVinyl">Inserer un vinyl</button>
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
                <button class="btn" @click="updateVinyl(record.id)">Modifier un vinyl</button>
                <button class="btn" @click="deleteVinyl(record.id)">Supprimer un vinyl</button>
            </div>
        </div>  </div>
</template>


<script>
import axios from 'axios'
import NavBar from "../components/NavBar.vue";
const API = 'http://localhost:8000/read.php'
const API_DELETE = 'http://localhost:8000/delete.php'
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
    },
    methods: {
        async deleteVinyl(recordId) {
            if (axios({
                method: 'delete',
                url: API_DELETE,
                data: {
                    id: recordId
                }
            })) {
                console.log('ok')

            } else {
                console.log('fuck')
            }
            await axios.get(API)
            this.$router.go()
        },
        createVinyl() {
            this.$router.push({ name: "create" })
        },
        updateVinyl(recordId) {
            this.$router.push({ name: 'update', params: { recordId: recordId } })
        }

    }
}

</script>

