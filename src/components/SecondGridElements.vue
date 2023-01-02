<template>
<div class="wrapper ">

   <div class="d-flex">
    <v-text-field
      label="Search for cities"
      :rules="rules"
      hide-details="auto"
      v-model="cityName"
      outlined
      class="rounded-lg"
    ></v-text-field>
   
     <div class="text-center">
    <v-btn
      color="deep-purple accent-4"
      class="white--text"
       height="3.5rem"
      @click="fetchingApi"
    >
      Search
      <v-icon right>
        mdi-open-in-new
      </v-icon>
    </v-btn>

    <v-overlay :value="overlay=loading">
      <v-progress-circular
        indeterminate
        size="64"
      ></v-progress-circular>
    </v-overlay>
  </div>
  </div>
  
 
  <!--second section-->
  <div class=" secondInnerDiv mt-4 ">
      <v-row no-gutters >
          <!-- this is the first column-->
      <v-col
        v-for="n in 1"
        :key="n"
        cols="12"
      
        sm="6"
      >
        <v-card
          class="pa-2 pl-6 cards"
         
          tile
        >
        <!--firstinner column-->
       <h1>{{cityName}}</h1>
       <h6>{{weather}}</h6>

       <h1 class="mt-15">{{temp}}°</h1>
        </v-card>

      </v-col>
      <!--this is the second column-->
       <v-col
        v-for="n in 1"
        :key="n"
        cols="12"
        sm="6"
      >
        <v-card
          class="pa-2 cards"
          
          tile
        >
        <!--second inner column-->
   <img class="img1" :src="imageDataLink" />
 
        </v-card>
      </v-col>
    </v-row>
  </div>
  <!--third inner div-->
  <div class="thirdInnerDiv rounded-xl pa-2 blue darken-5">
    <h5 style="color:white">TODAY'S FORECASTE</h5>
      <table>
        <tr>
          <td style="border:none">
            <ul>
              <li>
                <h5><b> 6:00 AM</b></h5>
              </li>
              <li>
                <img src="https://d1nhio0ox7pgb.cloudfront.net/_img/v_collection_png/512x512/shadow/cloud.png" alt="loading" style="height:3rem;width:3rem">
              
              </li>
              <li>
                <h3> <b>25° {{minTempC}}</b></h3>
              </li>
            </ul>
          </td>
          <td>
            <ul>
              <li>
                <h5><b> 6:00 AM</b></h5>
              </li>
              <li>
                <img src="data:image/jpeg;base64,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" alt="loading" style="height:3rem;width:3rem">
              
              </li>
              <li>
                <h3> <b>28°</b></h3>
              </li>
            </ul>
          </td>
          <td>
            <ul>
              <li>
                <h5><b> 6:00 AM</b></h5>
              </li>
              <li>
                <img src="https://media.istockphoto.com/id/1362631208/vector/yellow-sun-with-rays-sun-star-3d-vector-icon-cartoon-minimal-style-summer-weather-nature.jpg?b=1&s=170667a&w=0&k=20&c=eiuz6Q6rIed1uGf-d2UkyJKJiEdsjh9ErG6yGmPP6I8=" alt="loading" style="height:3rem;width:3rem">
              
              </li>
              <li>
                <h3> <b>33°</b></h3>
              </li>
            </ul>
          </td>
          <td>
            <ul>
              <li>
                <h5><b> 6:00 AM</b></h5>
              </li>
              <li>
                <img src="https://media.istockphoto.com/id/1362631208/vector/yellow-sun-with-rays-sun-star-3d-vector-icon-cartoon-minimal-style-summer-weather-nature.jpg?b=1&s=170667a&w=0&k=20&c=eiuz6Q6rIed1uGf-d2UkyJKJiEdsjh9ErG6yGmPP6I8=" alt="loading" style="height:3rem;width:3rem">
              
              </li>
              <li>
                <h3> <b>34°</b></h3>
              </li>
            </ul>
          </td>
          <td>
            <ul>
              <li>
                <h5><b> 6:00 AM</b></h5>
              </li>
              <li>
                <img src="https://d1nhio0ox7pgb.cloudfront.net/_img/v_collection_png/512x512/shadow/cloud.png" alt="loading" style="height:3rem;width:3rem">
              
              </li>
              <li>
                <h3> <b>32°</b></h3>
              </li>
            </ul>
          </td>
          <td>
            <ul>
              <li>
                <h5><b> 6:00 AM</b></h5>
              </li>
              <li>
                <img src="data:image/jpeg;base64,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" alt="loading" style="height:3rem;width:3rem">
              
              </li>
              <li>
                <h3> <b>30°</b></h3>
              </li>
            </ul>
          </td>
        </tr>
      </table>
  </div>
  
    <div class="thirdInnerDiv innerdiv2 rounded-xl pa-2 mt-5 blue darken-5" style="border:none ">
      <span class="d-flex justify-space-between">
       <h5 style="color:white">AIR CONDITIONS</h5>
        <v-btn
      depressed
      height="1.4rem"
      
   
      class="rounded-pill pa-2"
      color="primary"
    >
     see more
    </v-btn>
    </span>

    <table style="border:none">
      <tr>
         <td>
           
            <table class="nTable" style="width:20%">
              <tr>
                <td style="padding-left:3rem">
                  <v-icon>
                    mdi-thermometer
                  </v-icon>
                 
                </td>
                <td>
                     <h4 style="margin-left:25px !important">Real Feel</h4>
                </td>
                
              </tr>
              <tr>
                <td col-span-2 >
                 
                  <h1 class="ml-12">{{windDegree}}°</h1>
                
                </td>
              </tr>
            </table>
         </td>
         <td>
           <table style="width:20%">
              <tr>
                <td style="padding-left:3rem">
                  <v-icon>
                    mdi-weather-dust
                  </v-icon>
                 
                </td>
                <td>
                     <h4 style="margin-left:25px !important">Wind</h4>
                </td>
                
              </tr>
              <tr>
                <td col-span-2 >
                 
                  <h1 class="ml-12">{{windSpeed}}</h1>
                
                </td>
              </tr>
            </table>
         </td>
      </tr>
      <tr>
    <td>
      <table style="width:20%">
              <tr>
                <td style="padding-left:3rem">
                  <v-icon>
                    mdi-water

                  </v-icon>
                 
                </td>
                <td>
                     <h4 style="margin-left:25px !important">Chance of rain</h4>
                </td>
                
              </tr>
              <tr>
                <td col-span-2 >
                 
                  <h1 class="ml-12">{{rainDescription}}</h1>
                
                </td>
              </tr>
            </table>
    </td>
    <td>
      <table style="width:20%">
              <tr>
                <td style="padding-left:3rem">
                  <v-icon>
                    mdi-sun-thermometer
                  </v-icon>
                 
                </td>
                <td>
                     <h4 style="margin-left:25px !important">Clouds index</h4>
                </td>
                
              </tr>
              <tr>
                <td col-span-2 >
                 
                  <h1 class="ml-12">3</h1>
                
                </td>
              </tr>
            </table>
    </td>
      </tr>
    </table>
      </div>
     
  </div>
</template>
<script>

export default {
    name:'SecondGridElements',

    data(){
        return {
           loading:false,
            cityName:" islamabad",
            long:"",
            lat:"",
            weather:"clear",
            temp:"0",
            imgsrc:"https://openweathermap.org/img/wn/04n@2x.png",
            windSpeed:"0",
            windDegree:"0",
            rainDescription:"none",
            cloudsDescription:"none",
            
         
           
            country:""
           
        }
    },
      methods:{
       async fetchingApi()
      {

          setTimeout(() => {
           this.loading = true
        }, 1000);



        //https://api.openweathermap.org/data/2.5/weather?lat=31.582045&lon=74.329376&appid=
       await fetch(`http://api.openweathermap.org/geo/1.0/direct?q=${this.cityName}&limit=1&appid=a6263541248a7b7f620a62e5954a8f88`)
        .then((response)=>{
          return response.json();
        }).then((data)=>{
          console.log(data);

          this.long=data[0].lon;
          this.lat=data[0].lat;
         
        }).catch((err)=>{
            alert("error: " + err.message);
            console.log("error")
        })

       await  fetch(`https://api.openweathermap.org/data/2.5/weather?lat=${this.lat}&lon=${this.long}&appid=a6263541248a7b7f620a62e5954a8f88`)
        .then((response)=>{
          return response.json();
        }).then((data)=>{
          console.log(data);
   this.weather=data.weather[0].main;
    this.temp=Math.round( data.main.temp-273);
   this.imgsrc = `https://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png`;
        this.windSpeed=data.wind.speed;
        this.windDegree=data.wind.deg;
        this.rainDescription=data.weather[0].description;
        this.cloudsDescription=data.clouds.all;
         this.country=data.sys.country;

           setInterval(() => {
      
        this.loading=false;
    }, 2000);
        }).catch((err)=>{
            alert("error is here: " + err.message)
        })


       

      }
      
    },
    computed:{
    imageDataLink()
    {
      return this.imgsrc;
    }
    }
   

}
</script>
<style>
.secondInnerDiv{
    height: 250px;
  
}
.icon1::before{
    font-size: 10.7rem;

}
.thirdInnerDiv{
    border: 1px solid black;
    height: fit-content;
    margin: 0;
}
.thirdInnerDiv table{
  width: 100%;
}
.thirdInnerDiv table tr td{
  border-left: 1px solid rgb(202, 202, 202);
}
.thirdInnerDiv table tr td img{
  border-radius:10px;
}

h5{
  color:rgb(255, 255, 255)
}
.innerdiv2 tr td{
  border: none !important;
}
.img1{
      height: 10.4rem;
    margin-left: 7rem;
}
h1{
  color: white;
}
.cards{

 background-color:rgb(70, 149, 236) !important;
}
</style>