<template>
	<div class="container-center">
		<CardHeader />
	</div>
</template>

<script>
import CardHeader from "./components/CardHeader.vue";
export default {
	name: "App",
	components: { CardHeader },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap");
#app {
	font-family: "Roboto", sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	color: #fefae0;
	background-color: #fefae0;
}
.container-center {
	display: flex;
	height: 100vh;
	justify-content: center;
	align-items: center;
}
.card {
	width: 500px;
	padding: 40px 30px 20px 30px;
	background-color: #023047;
	border-radius: 50px;
}
</style>
