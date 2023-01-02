<template>

    <div class="main d-flex flex-column rounded-xl blue darken-5 " >
        <h2 style="color:white; text-aliegn:center">Enter the city and coutry name to see the forecast</h2>
         <div>
    <v-text-field
      label="City Name"
      :rules="rules"
      hide-details="auto"
      v-model="cityName"
    ></v-text-field>
    <v-text-field label="Country Name" v-model="countryName"></v-text-field>
  </div>
  <h3  style="color:white; text-aliegn:center">{{cityName}} / {{countryName}}</h3>
       
     <div class="text-center">
    <v-btn
      color="deep-purple accent-4"
      class="white--text"
      @click="forcasting"
    >
     See forecast
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

        <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Today</li>
            <li >
               
                 <img  alt="" style="height:3rem;width:3rem"   :src= "FdayImg"> 
              
            </li>
            <li>
                {{weather1}}
            </li>
            <li>{{maxTempC}}/{{minTempC}}</li>
        </ul>
         <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Sunday</li>
            <li> 
                   <img  alt="" style="height:3rem;width:3rem"   :src= "SdayImg"> 
            </li>
            <li>
                {{Secweather1}}
            </li>
            <li>{{SecmaxTempC}}/{{SecminTempC}}</li>
        </ul>
         <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Monday</li>
            <li>
                   <img  alt="" style="height:3rem;width:3rem"   :src= "TdayImg"> 
            </li>
            <li>
                {{Thiweather1}}
            </li>
            <li>{{ThimaxTempC}}/{{ThiminTempC}}</li>
        </ul>
         <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Tuesday</li>
            <li>
                   <img  alt="" style="height:3rem;width:3rem"   :src= "FodayImg"> 
            </li>
            <li>
                {{Fourweather1}}
            </li>
            <li>{{FourmaxTempC}}/{{FourminTempC}}</li>
        </ul>
         <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Wednesday</li>
            <li>
                   <img  alt="" style="height:3rem;width:3rem"   :src= "FFdayImg"> 
            </li>
            <li>
               {{Fifweather1}}
            </li>
            <li>{{FifmaxTempC}}/{{FifminTempC}}</li>
        </ul>
         <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Thursday</li>
            <li>
                  <img  alt="" style="height:3rem;width:3rem"   :src= "SIXdayImg"> 
            </li>
            <li>
               {{Sixweather1}}
            </li>
            <li>{{SixmaxTempC}}/{{SixminTempC}}</li>
        </ul>
         <ul class="d-flex justify-space-between mt-9" style="border-bottom:1px solid gray">
            <li>Friday</li>
            <li>
                   <img  alt="" style="height:3rem;width:3rem"   :src= "SEVdayImg"> 
            </li>
            <li>
               {{Sevweather1}}
            </li>
            <li>{{SevmaxTempC}}/{{SevminTempC}}</li>
        </ul>
       
    
    </div>
</template>
<script>

 export default {
    name:'ThirdGridElements',
    data(){
        return{
            loading:false,
            icon:"https://media.istockphoto.com/id/1362631208/vector/yellow-sun-with-rays-sun-star-3d-vector-icon-cartoon-minimal-style-summer-weather-nature.jpg?b=1&s=170667a&w=0&k=20&c=eiuz6Q6rIed1uGf-d2UkyJKJiEdsjh9ErG6yGmPP6I8=",
            minTempC:"11",
            maxTempC:"12",
            weather1:"Sunny",
          
            Secicon:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTxC8HdAscujQ6lOiQDD00dLdiZ0pNF-C8smowhRpUGYav0CyTOATUWzeNO6IM-eFPZaTI&usqp=CAU",
            SecminTempC:"12",
            SecmaxTempC:"13",
            Secweather1:"Cloudy",
         
            Thiicon:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTGwy2maGvphpBkVVIAARO8w2Km3tMAewK_Pw&usqp=CAU",
            ThiminTempC:"13",
            ThimaxTempC:"16",
            Thiweather1:"Rainny",
          
            Fouricon:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR4J5WJ_tCkxPKB-Ym1gnb03gQu0fu-ntSGAQ&usqp=CAU",
            FourminTempC:"16",
            FourmaxTempC:"22",
            Fourweather1:"Sun Rain",
          
            Fificon:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQtTt-Ltsg76bpFUOQJzuLxwkVKH_PrN4aIbQ&usqp=CAU",
            FifminTempC:"18",
            FifmaxTempC:"20",
            Fifweather1:"Cloudy Sun rain",
          
            Sixicon:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcScobAvjT3xivQ9imUNtKkdmhxa1txm0H9Q7A&usqp=CAU",
            SixminTempC:"9",
            SixmaxTempC:"11",
            Sixweather1:"Cloudy Sun",
         
            Sevicon:"https://media.istockphoto.com/id/1362631208/vector/yellow-sun-with-rays-sun-star-3d-vector-icon-cartoon-minimal-style-summer-weather-nature.jpg?b=1&s=170667a&w=0&k=20&c=eiuz6Q6rIed1uGf-d2UkyJKJiEdsjh9ErG6yGmPP6I8=",
            SevminTempC:"20",
            SevmaxTempC:"22",
            Sevweather1:" Clear",
           
           cityName:"Islamabad",
           countryName:"Pakistan"
          

        }
    },
  
    methods:{
        forcasting()
        {
            setTimeout(() => {
           this.loading = true
        }, 1000);
           
                    const options = {
	method: 'GET',
	headers: {
		'X-RapidAPI-Key': 'cb317de3eemsh321973d11497a40p1b0af3jsnb28b4969959b',
		'X-RapidAPI-Host': 'aerisweather1.p.rapidapi.com'
	}
};

  fetch(`https://aerisweather1.p.rapidapi.com/forecasts/${this.cityName},${this.countryName}`, options)
	.then((response)=>{
    return response.json();
  })
	.then((response=>{
    console.log(response);
   
      this.icon = `https://openweathermap.org/img/wn/${response.response[0].periods[0].icon}@2x.png`;
      this.minTempC=`${response.response[0].periods[0].minTempC}`;
    
    this.maxTempC=`${response.response[0].periods[0].maxTempC}`; 
    
    this.weather1=`${response.response[0].periods[0].weather }`;
  //second day data
   this.Secicon=`${response.response[0].periods[1].icon}`;
      this.SecminTempC=`${response.response[0].periods[1].minTempC}`;
    
    this.SecmaxTempC=`${response.response[0].periods[1].maxTempC}`; 
    
    this.Secweather1=`${response.response[0].periods[1].weather }`;
    //third day data
      this.Thiicon=`${response.response[0].periods[2].icon}`;
      this.ThiminTempC=`${response.response[0].periods[2].minTempC}`;
    
    this.ThimaxTempC=`${response.response[0].periods[2].maxTempC}`; 
    
    this.Thiweather1=`${response.response[0].periods[2].weather }`;
    // four day data
     this.Fouricon=`${response.response[0].periods[3].icon}`;
      this.FourminTempC=`${response.response[0].periods[3].minTempC}`;
    
    this.FourmaxTempC=`${response.response[0].periods[3].maxTempC}`; 
    
    this.Fourweather1=`${response.response[0].periods[3].weather }`;
    //fifth day data
      this.Fificon=`${response.response[0].periods[4].icon}`;
      this.FifminTempC=`${response.response[0].periods[4].minTempC}`;
    
    this.FifmaxTempC=`${response.response[0].periods[4].maxTempC}`; 
    
    this.Fifweather1=`${response.response[0].periods[4].weather }`;
    // sixth day data
      this.Sixicon=`${response.response[0].periods[5].icon}`;
      this.SixminTempC=`${response.response[0].periods[5].minTempC}`;
    
    this.SixmaxTempC=`${response.response[0].periods[5].maxTempC}`; 
    
    this.Sixweather1=`${response.response[0].periods[5].weather }`;
    //seventh day data
     this.Sevicon=`${response.response[0].periods[6].icon}`;
      this.SevminTempC=`${response.response[0].periods[6].minTempC}`;
    
    this.SevmaxTempC=`${response.response[0].periods[6].maxTempC}`; 
    
    this.Sevweather1=`${response.response[0].periods[6].weather }`;
    
  
     
    setInterval(() => {
      
        this.loading=false;
    }, 2000);
    
    console.log(this.objectData[0].periods[1].dateTimeISO);
  }))
  
	.catch(err => console.error(err));
        }
    },
    computed:{
        FdayImg()
        {
            return this.icon;
        },
         SdayImg()
        {
            return this.Secicon;
        },
          TdayImg()
        {
            return this.Thiicon;
        },
          FodayImg()
        {
            return this.Fouricon;
        },
          FFdayImg()
        {
            return this.Fificon;
        },
          SIXdayImg()
        {
            return this.Sixicon;
        },
          SEVdayImg()
        {
            return this.Sevicon ;
        }
    }
}
</script>
<style>
.main{
   
    height:fit-content;
    padding: 2rem;
    padding-top: 1rem;
    background-color: rgb(218, 218, 218);
   
}
.spinner {
  height: 20px;
  width: 20px;
  
}
</style>