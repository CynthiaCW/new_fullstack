<template>
 <div>
        <div class="courses-container">
          <h1>Découvrez nos vinyls</h1>
          <button class="btn"  methods='GET' href="">Ajouter un vinyls</button> 
            <div class="course">
                <div class="course-preview">
                    <slot>
                        <h2>En stock</h2>
                        <img class="main-image" src="static/img/81aTawcGdmL._SL1500_.jpg" height='200px' href="#"/>
                    </slot>
                </div>
                <div class="course-info">
                    <h6>Nom du groupe</h6>
                    <h6>Year</h6>
                    <h6>Genre</h6>
                    <h2>Titre du vinyls</h2>

                    <p>Description</p>
    
                </div>
                <button class="btn" methods='PUT' href="">Modifier un vinyls</button> 
                <button class="btn" methods='DELETE' href="">Supprimer un vinyls</button> 
            </div>
            
        </div>
 </div>
</template>