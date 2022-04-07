<template>
    <div>
        <div class="courses-container">
          <h1>Découvrez nos vinyls</h1>
            <div class="course">

                <h3>En stock</h3>

                <div class="course-preview">
                    <slot>
                        <h6>Course par défaut </h6>
                        <h2>En stock</h2>
                        <img class="main-image" src="" height='200px' href="#"/>
                    </slot>
                </div>
                <div class="course-info">
                    <h6>Nom du groupe</h6>
                    <h6>Year</h6>
                    <h6>Genre</h6>
                    <h2>Titre du vinyls</h2>

                    <p>Description</p>

                </div>
            </div>
        </div>
      </div>
</template>
