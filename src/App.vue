<template class="er">
   <div class="app">
    <div class="rect3" >
      <Pane1 @getsearch="retdetails"/>
      <Info v-if="typeof weather.main !='undefined'" :weat="weather.weather[0].main" :min="weather.main.temp_min" :max="weather.main.temp_max" :hum="weather.main.humidity" :pre="weather.main.pressure" :vis="weather.visibility"/>
      <Info2 v-if="typeof weather.main !='undefined'" style="margin-top: 0px;" :ritime="rtime" :setime="stime" :wspeed="weather.wind.speed" :deg="weather.wind.deg"/>
    </div>  
   </div>
</template>

<script>

//import Temp from '@/components/temp.vue'
import Pane1 from '@/components/pane1.vue'
import Info from '@/components/info.vue'
import Info2 from '@/components/info2.vue'

export default {
  name: 'App',
  components:{
    Pane1,
    Info,
    Info2
  },
  data () {
    return{
      api_key: 'your api key',
      url_base: 'https://api.openweathermap.org/data/2.5/',
      query: 'Puri',
      weather: {},
      rtime: '',
      stime: ''
    }
  },
  methods:{
      setResults(results){
        this.weather = results;
      },
      retdetails(search){
        fetch(`${this.url_base}weather?q=${search}&units=metric&APPID=${this.api_key}`).then(res=>{
          return res.json();
        }).then(this.setResults);
        let date1= new Date(this.weather.sys.sunrise * 1000);
        this.rtime=`${date1.getHours()%12}:${date1.getMinutes()}`;
        let date2= new Date(this.weather.sys.sunset * 1000);
        this.stime=`${date2.getHours()%12}:${date2.getMinutes()}`;
      }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@200;300&display=swap');
body{
  
  
  margin: 0;
  padding: 0;
  
  background: linear-gradient(45deg,#99F6FF,#B1D93A);
  background-size: 400% 800%;
  background-repeat: no-repeat;
  animation: gradient 20s linear infinite;

}
@keyframes gradient {
  0% {
      background-position: 0% 50%;
  }
  50% {
      background-position: 100% 50%;
  }
  100% {
      background-position: 0% 50%;
  }
}
.rect3{
  padding: 0;
}
.app{
  padding: 0;
}
</style>
