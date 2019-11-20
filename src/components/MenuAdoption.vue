<template>
    <div>
        <nav class="navbar navbar-expand-md navbar-dark  fixed-top">   
            <button class="navbar-toggler" type="bytton" data-toggle="collapse" data-target="#navbarResponsive">
                <span class="navbar-toggler-icon" ></span>
            </button>          
            <div class="collapse navbar-collapse" id="navbarResponsive">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item">
                        <router-link to="/" >Inicio</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/cats" >Gatos</router-link>
                    </li>
                    <li class="nav-item">
                      <router-link to="/dogs" >Perros</router-link>
                    </li> 
                </ul>
            </div>
        </nav>
        <div>
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
export default {

  name: 'MenuAdoption',

  data () {
    return {

    }
  }
}
</script>
