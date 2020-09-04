<template>
<div>
	<div v-for="(personaje,i) in personajes" :key="i" >
		<Personaje :src="personaje.imagen" :msg="personaje.nombre" />
	</div>
</div>	
</template>

<script>
import Personaje from './components/Personaje';
export default { 
	components: {
		Personaje,
	},
	data() {
		return {
			personajes: [],
		};
	},
	mounted() {
		fetch('https://rickandmortyapi.com/api/character')
			.then((resp) => resp.json())
			.then((json) => {
				let data = json.results;
				data.slice(0,10).forEach((element) => {
					let nombre = element.name;
					let imagen = element.image;
					this.personajes.push({ nombre, imagen });
				});
			})
			.catch((error) => console.log(`Estas en un error Rick ${error}`));
	},
};
</script>

<style >
body{
	background-image: url("https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png");
	background-repeat: no-repeat;
	background-size: cover;
}
div{
	display: flex;
	flex-flow: column;
	color: green;
	font-family: fantasy;
}

</style>



