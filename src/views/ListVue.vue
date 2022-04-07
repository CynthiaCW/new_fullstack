<div>
        <div class="courses-container">
          <h1>Découvrez nos vinyls</h1>
            <div class="course">
                <div class="course-preview" :style="{backgroundColor:cardColor}">
                    <slot>
                        <h2>En stock</h2>
                        <img class="main-image" src="static/img/81aTawcGdmL._SL1500_.jpg" height='200px' href="#"/>
                    </slot>
                </div>
                <div class="course-info">
                    <h6>Nom du groupe {{chapNumber}}</h6>
                    <h2>Titre du vinyls{{Title}}</h2>
      
                    <button class="btn" @click="selectCourse" href="#VinylsDetails.html">Voir</button>
                </div>
            </div>
        </div>
      </div>