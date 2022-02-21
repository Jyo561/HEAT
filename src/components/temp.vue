<template>
	<div class="temp">
		<h1>45&#176;C</h1>
		
	</div>
</template>

<script>
	export default{
		name: 'Temp',
	}
</script>

<style>
	.temp{
		background-color: rgba(255, 255, 255, 0.25);
		width: 300px;
		height: 200px;
		position: relative;
		left: 500px;
		border-radius: 16px;
		font-size: 45px;
		top: 100px;
	}
	h1{
		text-align: center;
		top: 35px;
		margin: 50px 0px;
		position: relative;
		color: #fff;
	}
</style>
