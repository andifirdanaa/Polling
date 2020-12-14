<template>
  <div class="buttons">

   <button v-for="(emoticon, index) in emoticons"
   			:key="index"
   			:id="emoticon"
   			:value="emoticon"
   			class="btn-emoticon"
   			@click ="vote">
   				
   </button>


  </div>
</template>

<script>
// @ is an alias to /src
import moment from "moment";

export default {
  name: "Vote",
  components: { },
  data: function () {
  	return{
  		 emoticons : ['very-bad','bad','okay','good','very-good']
  	}
  },
  methods:{
  	vote(e){
  		var voted = e.target.value;

  		//moment waktu
  		var keyStorages = moment().format('YYYYMMDD,h:mm:ss')
  		var waktu = moment().format('YYYY-MM-DD , h:mm:ss')

  		//membuat data json
  		var data = {
  			vote : voted,
  			create_at : waktu
  		}
  		console.log(data);
  		//menjadikan data json ke string
  		var jsonToString = JSON.stringify(data);
  		console.log(jsonToString);

  		localStorage.setItem(keyStorages,jsonToString);
  	}
  }
};
</script>

<style type="text/css">
	.buttons{
		display: flex;

	}
	.btn-emoticon{
		background: url('~@/assets/emoticon.png');
		width: 101px;
		height: 100px;
		border: none;
		margin: 0px 10px;
		cursor: pointer;
		outline: none;
	}
	#very-bad{
		background-position: 0px 0px; 
	}
	#very-bad:hover{
		background-position: 0px -100px; 
	}
	#very-bad:active{
		background-position: 0px -200px; 
	}
	#bad{
		background-position: -101px 0px; 
	}
	#bad:hover{
		background-position: -101px -100px; 
	}
	#bad:active{
		background-position: -101px -200px; 
	}
	#okay{
		background-position: -202px 0px; 
	}
	#okay:hover{
		background-position: -202px -202px; 
	}
	#okay:active{
		background-position: -202px -200px; 
	}
	#good{
		background-position: -302px 0px; 
	}
	#good:hover{
		background-position: -302px -202px; 
	}
	#good:active{     
		background-position: -302px -200px; 
	}#very-good{
		background-position: -402px 0px; 
	}
	#very-good:hover{
		background-position: -402px -202px; 
	}
	#very-good:active{
		background-position: -402px -200px; 
	}
</style>
