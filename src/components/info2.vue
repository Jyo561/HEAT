<template>
	<div class="bars">
		<div class="com1">
			<div class="rect"><img src="../assets/lqk7sj.svg" class="sun" alt="">:<p class="rom1">{{ ritime }}<span>AM</span></p><br></div>
			<div class="rect"><img src="../assets/kdcqf8.svg" class="sun" alt="">:<p class="rom1">{{ setime }} <span>PM</span></p></div>
		</div>
		<div>
			<img src="../assets/win.svg" alt="">
		</div>
		<div class="com2">
			<p>Wind Speed: <span>{{ wspeed }} <span style="color: burlywood;">km/h</span></span> </p>
			<p>Wind Direction: <span v-if="((deg>337.5 && deg<360) || (deg>0 && deg<22.5))">N</span> <span v-if="deg>22.5 && deg<67.5">NE</span><span v-if="deg>67.5 && deg<112.5">E</span><span v-if="deg>122.5 && deg<157.5">SE</span><span v-if="deg>157.5 && deg<202.5">S</span><span v-if="deg>202.5 && deg<247.5">SW</span><span v-if="deg>247.5 && deg<292.5">W</span><span v-if="deg>292.5 && deg<337.5">NW</span></p>
		</div>
	</div>	
</template>

<script>
	export default{
		name: 'Info2',
		props:[
			'ritime',
			'setime',
			'wspeed',
			'deg'
		]
	}
</script>

<style>
	.sun{
		width: 120px;
		height: 100px;
	}
	.com1{
		display: block;
		margin-top: 10px;
		margin-left: 10%;
	}
	.rect{
		display: flex;
	}
	.rom1{
		margin-left: 4em;
		font-size: 40px;
		margin-top: 18px;
	}
	.com2{
		width: 250px;
		height: 220px;
		margin-left: 15%;
		background-size: cover;
		background-repeat: no-repeat;
		font-size: 25px;
		padding-top: 40px;
	}
</style>
