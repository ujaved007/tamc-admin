<template>
	<div class="container-center">
		<div class="card">
			<card-header @add-name="addName" />
			<card-body :staffNames="staffNames" @handle-delete="handleDelete" />
		</div>
	</div>
</template>

<script>
import axios from "axios";

import CardHeader from "./components/CardHeader.vue";
import CardBody from "./components/CardBody.vue";

export default {
	name: "App",
	components: { CardHeader, CardBody },
	data() {
		return {
			staffData: [],
			staffNames: [],
		};
	},
	methods: {
		async fetchStaff() {
			const res = await fetch(process.env.VUE_APP_API_URL);
			const data = await res.json();
			return data;
		},
		async updateStaff(id, data) {
			try {
				await axios(`${process.env.VUE_APP_LOCAL_URL}/${id}`, {
					method: "PATCH",
					data: data,
				});
			} catch (error) {
				console.log(error);
			}
		},
		async handleDelete(item) {
			const newArr = this.staffNames.filter((staff) => staff !== item);
			this.staffNames = newArr;
			await this.updateStaff(this.staffData[0]._id, { data: newArr });
		},
		async addName(name) {
			const newArr = [...this.staffNames, name];
			const sortedArr = newArr.sort();
			this.staffNames = sortedArr;
			await this.updateStaff(this.staffData[0]._id, { data: sortedArr });
		},
	},
	async created() {
		this.staffData = await this.fetchStaff();
		this.staffNames = await this.staffData[0].data;
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
