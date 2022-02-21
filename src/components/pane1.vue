<template>
	<div style="display: flex;">
		<div>
			<h1 class="time">HEAT</h1>
			<p class="date">{{ timestamp }}</p>
		</div>
		<div class="som">
			<span class="sea"><input class="inp" v-model="search" type="text" placeholder="Search" @keypress="callap" ><button class="btn" @click="callap"><img src="../assets/searchsolid.svg" alt="" style="height: 23px;top: 2px;position: relative;" class="sear" ></button></span>
		</div>
	</div>
</template>

<script>


export default{
	name: 'pane1',
	data () {
		return{
			search:'',
			timestamp:''
		}
	},
	methods:{
		callap(){
			this.$emit("getsearch",this.search);
		},
		created() {
                setInterval(this.getNow, 1000);
            },
		getNow: function() {
                    const today = new Date();
                    const date = today.getFullYear()+'-'+(today.getMonth()+1)+'-'+today.getDate();
                    const time = today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds();
                    const dateTime = date +' '+ time;
                    this.timestamp =""+dateTime;
                }
	}
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Merienda&display=swap');
.am{
	font-size: 20px;
}
.time{
	font-size: 80px;
	font-family:  "Merienda", Helvetica, Arial;
	color: blue;
	margin-left: 100px;
}
.date{
	color: black;
	font-size: 20px;
	margin-left: 100px;
	margin-top: -60px;
}
.som{
	margin-top: 90px;
	padding-left: 400px;
}
.inp{
	outline: none;
	background: none;
	border: none;
	transform: scale(1.0);
	font-size: 20px;
	color: black;
}
.sea{
	position: realtive;
	margin-left: 200px;
	transform: scale(1.0);
	border-bottom: 2px solid white;
}
.btn{
	background: none;
	outline: none;
	border: none;
}
</style>