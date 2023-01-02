<template >

   <ul>
       <li class="list pl-2 rounded-lg blue darken-5 ">
       <v-icon outlined class="pa-2 white--text lighten-5 ">
                mdi-weather-dust

            </v-icon>
       </li>
       <li class="mt-10 d-flex flex-column">

           <v-icon outlined class=" mr-2 black--text lighten-5  ">
                mdi-weather-partly-cloudy

            </v-icon>
            <h3>Weather</h3>
       </li>
       <li>
         <v-icon outlined class=" mr-2 gray--text lighten-5 ">
                mdi-format-list-bulleted

            </v-icon>
          <h5 class="gray--text" >Cities</h5>
          </li>
       <li>
             <v-icon outlined class=" mr-2 gray--text lighten-5 ">
                mdi-map

            </v-icon>
<h5 class="gray--text" >Map</h5>
       </li>
       <li>
             <v-icon outlined class=" mr-2 gray--text lighten-5 ">
                mdi-tune

            </v-icon>
        <h5 class="gray--text" >Setting</h5>
       </li>
       

   </ul>
  
</template>
<script>
export default {
    name:'FirstGridElements'
}
</script>
<style>
ul{
    list-style: none;
    padding: 0 !important;
}
.list{
    border: 1px solid black;
    height: fit-content;
    width: 4rem;

}
ul li {
    line-height: 3rem;
    text-align: center;
}


</style>