<template>
      <nav class="navbar">
   
    <ul>
      <img class="navbar-brand" src="" height='100px'> 
        <!-- todo src -->

        <li class="nav-item active">
        <a class="nav-link" href="">Home</a>
      </li>

      <li class="nav-item active">
        <a class="nav-link" href="">Se connecter</a>
      </li>
      
      <li class="nav-item active">
        <a class="nav-link" href="">Nos Vinyls</a>
      </li>

      

    </ul>
  </nav>

</template>

<style scoped>

.navbar {
    background-color: rgb(34, 34, 34);
    margin: 15px;
    height: 100%;
    width: 400px;
    position: fixed; /* Fixed Sidebar (stay in place on scroll) */
    z-index: 1; /* Stay on top */
    top: 0; /* Stay at the top */
    left: 0;
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 20px;
    border-radius: 25px;
    border: #7B6DED;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

ul {
    padding-left: 40px;
}

ul>li {
    text-decoration: none;
    list-style-type: none;
    padding: 40px;
    display: block;

}
ul>li>a {
    text-decoration: none;
    font-family: 'Poppins';
    font-size: 1.5rem;
    color: white;

}

ul>li>a:hover {
    color: #7B6DED;
}

/*---------------------------*/

</style>