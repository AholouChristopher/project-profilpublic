<template>
	<div class=" flex justify-center my-14">
		<div class="flex flex-col lg:flex-row my-14" style="width:60vw;">
			<div class="flex items-center basis-1/2 max-lg:mb-5">
				<h1 class="text-2xl font-bold md:text-3xl lg:text-4xl max-lg:text-center max-lg:mx-auto" >Trouver un job <br class="max-lg:hidden"/>dans le secteur Public</h1>
			</div>
			<div class="flex basis-1/2 relative" style="background-color: #58d9db; border-radius: 10px;padding: 10px">
				<div class="flex flex-col justify-center" style="width:100%; padding:1rem;">
					<input type="text" placeholder="Votre prochain job ?">
					<input type="text" placeholder="Où ?" style="width: 60%;">
				</div>
				<button style="position: absolute; top:85%; left:10%; width: 25%; height:3rem ;background: linear-gradient(white, #58d9db );border-radius: 10px; font-weight: bold;"> Voir les jobs</button>
			</div>
		</div>
	</div>
	<div class="mx-auto flex justify-center mx-auto max-w-screen-xl px-4 py-12">
		<div>
			<h3 class="text-3xl font-bold">{{dataAPI.length}} offres</h3>
			<div class="flex flex-wrap justify-center">
				<Card  class="  mt-6" v-for="job,index in dataAPI" :key="index" :tabDataApiJob="job" />
			</div>
		</div>
	</div>
</template>
<script>
	import Card from '~/components/Card.vue';
	export default {
		components: {
			Card,
		}
		,  data(){
			return{
				dataAPI:[]
			}
		}
		,  created(){
			this.fetchGetDataAPI()
		}
		,  methods:{
			async fetchGetDataAPI (){
				const dataApi = await $fetch('https://app.staging.profilpublic.fr/api/jobs').then((res)=>{
					this.dataAPI = res.data;
					console.log(this.dataAPI);
				});
			}
		}
	}
</script>
<style scoped>
	input
	{
		border-radius: .25rem;
		border-width: 1px;
		border-color: #d4d4d8;
		padding: .25rem .25rem;
		margin:  0.5rem 0.25rem 0.5rem 0.25rem;
	}
</style>