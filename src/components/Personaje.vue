<template>
  <div>
    <img :src="src" alt="">
    <h3> {{msg}}</h3>
  </div>
</template>

<script>
export default {
   name: "Personaje",
   props: {
       src : String,
       msg : String,
   }
}
</script>

<style>
img{
	border-radius: 50%;
  width: 200px;
	height: 200px;
	background-position: center;
	background-size: cover;
	background-repeat: no-repeat;
}
img:hover {
	-webkit-transform: rotateY(180deg);
	-webkit-transform-style: preserve-3d;
	transform: rotateY(180deg);
	transform-style: preserve-3d;
}
h3{
  padding-left: 50px;
}

</style>
