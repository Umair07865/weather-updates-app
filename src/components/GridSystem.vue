  <template>

    <!-- 92c5b5d6bf81bb4e00b19a161887f90d -->
  <v-container-fluid class="grey ">
    <v-row no-gutters>
      <v-col
        v-for="n in 1"
        :key="n"
        cols="12"
        lg="1"
      >
        <v-card
          class="pa-2"
          outlined
          tile
             style="height:850px"
        >
        <!--this is the first grid inner wrapper-->
         <div class="innerWrapper  rounded-xl blue darken-5">
       <FirstGridElements/>
         </div>
        </v-card>
      </v-col>
      <!--this is the second middle grid-->
       <v-col
        v-for="n in 1"
        :key="n"
        cols="12"
        lg="7"
      >
        <v-card
          class="pa-2"
          outlined
          tile
             style="height:850px"
        >
        <!-- this is the second inner grid-->
        <div class="innerWrapper" style="border:none">
         <SecondGridElements/>
         </div>
        </v-card>
      </v-col>
      <!-- third grid-->
       <v-col
        v-for="n in 1"
        :key="n"
        cols="12"
        lg="4"
      >
        <v-card
          class="pa-2"
          outlined
          tile
          style="height:850px"
        >
       <!-- this is the third inner grid -->
       <div  class="innerWrapper" style="border:none; overflow-y:scroll ">

      
     <ThirdGridElements/>
      </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container-fluid>
</template>

<script>
import FirstGridElements from "./FirstGridElements.vue"
import SecondGridElements  from "./SecondGridElements.vue"
import ThirdGridElements  from "./ThirdGridElements.vue"
export default {
    name:'GridSystem',
    components:{

        FirstGridElements,
        SecondGridElements,
        ThirdGridElements
        
    },
  

}
</script>
<style>
.innerWrapper{

   border: 1px solid black;
    height: 750px;
    width: 90%;
    padding: 1rem;

}
</style>