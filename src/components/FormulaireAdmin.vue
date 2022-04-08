<template>
    <div>
        <form v-on:submit.prevent="submitForm">
            <h1>Ajouter un vinyls</h1>

            <div class="champs">
                <label for="text">Nom du groupe</label>
                <input type="text" id="name" name="band" required v-model="form.band" />
            </div>

            <div class="champs">
                <label for="text">Année</label>
                <input type="text" id="start" name="year" placeholder="2022-07-22" required v-model="form.year"/>
            </div>

            <div class="champs">
                <label for="text">Genre</label>
                <input type="text" id="name" name="genre" required v-model="form.genre"/>
            </div>

            <div class="champs">
                <label for="text">Description</label>
                <input type="text" id="name" name="description" v-model="form.description"/>
            </div>

            <div class="champs">
                <label for="text">Lien URL image</label>
                <input type="text" name="url" id="pic" required v-model="form.pic"/>
            </div>

            <div class="champs">
                <label for="checkbox">En stock</label>
                <input type="checkbox" name="si" value="1" v-model="form.si"/>
                <input type="checkbox" name="no"  value="0" v-model="form.no"/>
            </div>

            <div class="btnCentrer">
                <button class="btn" methods="POST"  @click="submitForm">Creer un vinyls</button>
            </div>
        </form>
    </div>
</template>

<script>
import axios from 'axios'
const API_CREATE = 'http://localhost:8000/create.php'

export default {
    name: 'FormulaireAdmin',
    data() {
        return {
            form: {
                picture: '',
                title: '',
                band: '',
                date: '',
                genre: '',
                description: '',
                available: ''
            }
        }
    },
    methods: {
        submitForm() {
            if (axios.put(API_CREATE, this.form)) {
                console.log('ok')
            } else {
                console.log('fuck')
            }

        }
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

form > .champs {
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