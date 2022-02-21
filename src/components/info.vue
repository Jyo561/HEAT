<template>
	<div class="bars">
		<div class="com" v-if="weat == 'Clear'">
			<img class="image" src="../assets/night.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Clouds'">
			<img class="image" src="../assets/cloudy.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Rain'">
			<img class="image" src="../assets/rainy-7.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Haze'">
			<img class="image" src="../assets/cloudy-night-3.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Mist'">
			<img class="image" src="../assets/rainy-4.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Snow'">
			<img class="image" src="../assets/night.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Smoke'">
			<img class="image3" src="../assets/Weather_Icons_-_smoke.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com" v-if="weat == 'Shower'">
			<img class="image3" src="../assets/rainy-5.svg" alt="">
			<p style="color: #fff;margin-top: -6%;margin-left: 55%;text-align: center;">{{ weat }}</p>
		</div>
		<div class="com di">
			<p>{{ min }}<sup>&#176;</sup>C - <span class="tex">Min Temp</span></p>
			<p>{{ max }}<sup>&#176;</sup>C - <span class="tex">Max Temp</span></p>
		</div>
		<div class="com">
			<img src="../assets/humidity-water-level-control-icon-vector-23391019.jpg" alt="" class="image2"><br>
			<p style="margin-left: 110px;">Humidity(%)</p>
			<span></span>
			<p class="rom">{{ hum }}</p>
		</div>
		<div class="com">
			<img src="../assets/Pressure.jpg" alt="" class="image2" />
			<p style="margin-left:100px">Pressure(in mm)</p>
			<span>
			<p class="rom" style="margin-left: 90px;">{{ pre }}</p>
			</span>
		</div>
		<div class="com">
			<img src="../assets/visibility.png" alt="" class="image2" />
			<p style="margin-left:95px">Visibility</p>
			<span>
			<p class="rom" style="margin-left: 90px;">{{ vis }}</p>
			</span>
		</div>
	</div>
</template>

<script>
export default{
	name: 'Info',
	props:[
		'weat',
		'min',
		'max',
		'hum',
		'pre',
		'vis'
	]
}
</script>

<style>
	.bars{
		width: 99.3vw;
		height: 220px;
		background-color: black;
		background: rgba(0,0,0,0.5);
		margin-top: 11%;
		margin-left: -14px;
		display: flex;
		padding:  5px;
	}
	.image{
		width: 250px;
		height: 200px;
		margin-left: 28%;
		margin-top: -10%;
		opacity: 1;
	}
	.com{
		display: block;
		opacity: 1.0 !important;
		text-align: center;
	}
	p{
		color: #fff;
	}
	.di{
		margin-top: -3.5%;
		margin-left: 10%;
		font-size: 50px;
	}
	.tex{
		font-size: 20px !important;
	}
	.rom{
		margin-left: 100px;
		font-size: 40px;
	}
	.image2{
		border-radius: 50%;
		width: 50px;
		height: 50px;
		margin-left: 100px;
		margin-top: 20px;
	}
	.image3{
		width: 200px;
		height: 180px;
		margin-left: 28%;
		margin-top: 0%;
		opacity: 1;
	}
</style>