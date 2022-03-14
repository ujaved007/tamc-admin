<template>
	<div class="container-center">
		<div class="card">
			<card-header />
			<card-body :staffNames="staffNames" />
		</div>
	</div>
</template>

<script>
import CardHeader from "./components/CardHeader.vue";
import CardBody from "./components/CardBody.vue";

export default {
	name: "App",
	components: { CardHeader, CardBody },
	data() {
		return {
			staffNames: [],
		};
	},
	methods: {
		async fetchStaff() {
			const res = await fetch(process.env.VUE_APP_API_URL);
			const data = await res.json();
			return data;
		},
	},
	async created() {
		this.staffNames = await this.fetchStaff();
	},
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
