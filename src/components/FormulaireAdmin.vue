<template>
    <div>
        <form v-on:submit.prevent="submitForm">
            <h1>{{(!form.id)?'Ajouter un vinyl':'Modifier un vinyl'}}</h1>
            <!--<input type="text" v-model="form.id">-->
            <div class="champs">
                <label for="pic">Lien URL image</label>
                <input type="text" name="picture_link" id="pic" required v-model="form.picture_link">
            </div>

            <div class="champs">
                <label for="title">Nom du vinyl</label>
                <input type="text" id="title" name="title" required v-model="form.title" />
            </div>
            <div class="champs">
                <label for="band">Nom du groupe</label>
                <input type="text" id="band" name="band" required v-model="form.band" />
            </div>
            <div class="champs">
                <label for="year">Année</label>
                <input type="date" id="year" name="year_release" required v-model="form.year_release" />
            </div>

            <div class="champs">
                <label for="genre">Genre</label>
                <input type="text" id="genre" name="genre" required v-model="form.genre" />
            </div>

            <div class="champs">
                <label for="description">Description</label>
                <textarea name="description" id="description" cols="30" rows="10" v-model="form.description" />
            </div>

            <div class="champs">
                <label for="checkbox">En stock</label>
                <input type="checkbox" name="available" v-model="form.available" />
            </div>

            <div class="btnCentrer">
                <button class="btn">{{(!form.id)?'Creer un vinyl':'Modifier un vinyl'}}</button>
            </div>
        </form>  </div>
</template>

<script>
import axios from 'axios'
const API_CREATE = 'http://localhost:8000/create.php'
const API_SINGLE_READ = 'http://localhost:8000/single_read.php/?id='
const API_UPDATE = 'http://localhost:8000/update.php'

export default {
    name: 'FormulaireAdmin',
    data: () => ({

        form: {
            id: '',
            picture_link: '',
            title: '',
            band: '',
            year_release: '',
            genre: '',
            description: '',
            available: ''
        },
        record: {}
    }),
    methods: {
        async submitForm() {
            if (!this.form.id) {
                if (await axios.post(API_CREATE, this.form)) {
                    this.$router.push({ name: 'admin' })
                    console.log('created')
                } else {
                    console.log('fuck')
                }
            } else {
                if (await axios.put(API_UPDATE, this.form)) {
                    this.$router.push({ name: 'admin' })
                    console.log('updated')
                } else {
                    console.log('fuck')
                }
            }




        }
    },
    async created() {
        const { recordId } = this.$route.params
        const apiDetailsUri = API_SINGLE_READ + recordId
        const oneRecord = await axios.get(apiDetailsUri)
        this.record = oneRecord.data
        this.form.id = this.record.id
        this.form.picture_link = this.record.picture_link
        this.form.title = this.record.title
        this.form.band = this.record.band
        this.form.year_release = this.record.year_release
        this.form.genre = this.record.genre
        this.form.description = this.record.description
        this.form.available = this.record.available
    }
}


</script>

<style scoped>
/* Fonts Titre */
@import url("https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

/* Fonts texte */
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

form {
    background-color: #fff;
    font-family: "Poppins";
    border-radius: 10px;
    box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
    display: flex;
    flex-direction: column;

    max-width: 100%;
    margin: 20px;
    overflow: hidden;
    width: 563px;
}

form>.champs {
    display: flex;
    flex-direction: column;
    align-content: center;
    padding: 15px;
}

label {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    color: #7b6ded;
}

input {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    border: 1.5px solid;
    border-radius: 6px;
    width: 50%;
    height: 50%;
    border-color: #838383;
}

.btnCentrer {
    display: flex;
    justify-content: center;
    padding: 15px;
}

.btn {
    background-color: #7b6ded;
    border: 0;
    border-radius: 10px;
    box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
    color: #fff;
    font-size: 16px;
    padding: 12px 25px;
    bottom: 30px;
    right: 30px;
    letter-spacing: 1px;
}

.btn:hover {
    background-color: #533ef0;
}

h1 {
    font-family: "Poppins";
    padding: 15px;
}
</style>