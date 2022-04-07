<template>
 <div>
        <h1>Ajouter un nouveau vinyls</h1>
       
        <AdminVue />

        <div class="btnCentrer">
            <button class="btn" methods='PUT' href="">Modifier un vinyls</button> 
            <button class="btn" methods='DELETE' href="">Supprimer un vinyls</button> 
        </div>
 </div>
</template>

<script>
// @ is an alias to /src
import AdminVue from '@/components/AdminVue.vue'

export default {
  name: 'AdminVue',
  components: {
    AdminVue
  }
}
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

/* Fonts texte */
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

.btnCentrer {
    display: flex;
    justify-content: space-between;
    padding: 15px;
}
.btn {

	background-color: #7B6DED;
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
    font-family: 'Poppins';
   padding: 15px; 
}


</style>