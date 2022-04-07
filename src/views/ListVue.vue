<template>
    <div>
        <div class="courses-container">
          <h1>Découvrez nos vinyls</h1>
            <div class="course">
                <div class="course-preview">
                    <slot>
                        <h2>En stock</h2>
                        <img class="main-image" src="static/img/81aTawcGdmL._SL1500_.jpg" height='200px' href="#"/>
                    </slot>
                </div>
                <div class="course-info">
                    <h6>Nom du groupe </h6>
                    <h2>Titre du vinyls</h2>
      
                    <button class="btn"  href="">Voir</button> 
                    <!-- @click="selectCourse" -->
                </div>
            </div>
        </div>
      </div>
</template>

