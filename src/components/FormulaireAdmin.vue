<template>
    <form action="" method="post">

        <h1>Ajouter un vinyls</h1>

        <div class="champs">
            <label for="text">Nom du groupe</label>
            <input type="text" id="name" name="user_name" required>
        </div>
    
        <div class="champs">
            <label for="text">Année</label>
            <input type="date" id="start" name="trip-start"
             value="2022-07-22" required>
        </div>
    
        <div class="champs">
            <label for="text">Genre</label>
            <input type="text" id="name" name="user_name" required>
        </div>
    
        <div class="champs">
            <label for="text">Description</label>
            <input type="text" id="name" name="user_name">
        </div>
    
        <div class="champs">
            <label for="text">Lien URL image</label>
            <input type="text" name="url" id="url"
            required>
        </div>
    
          <div class="btnCentrer">
            <button class="btn" methods="POST" type="submit">Creer un vinyls</button>
        </div>
    </form>
</template>

<style scoped>
/* Fonts Titre */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

/* Fonts texte */
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

form {

    background-color: #fff;
    font-family: 'Poppins';
	border-radius: 10px;
	box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
	display: flex;
    flex-direction: column;

	max-width: 100%;
	margin: 20px;
	overflow: hidden;
	width: 563px;
}

form >.champs {
    display: flex;
    flex-direction: column;
    align-content: center;
    padding: 15px;
}
label {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    color: #7B6DED;
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