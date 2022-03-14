<template>
	<form @submit="onSubmit">
		<input type="text" v-model="guard" name="guard" placeholder="enter guard's name..." />
		<button type="submit">Add</button>
	</form>
</template>

<script>
export default {
	name: "AddGuard",
	data() {
		return {
			guard: "",
		};
	},
	methods: {
		onSubmit(e) {
			e.preventDefault();
			if (!this.guard) {
				alert("please type a name");
				return;
			}
			this.$emit("add-name", this.guard);
			this.guard = "";
		},
	},
};
</script>

<style scope>
form {
	display: grid;
	grid-template-columns: 1fr 0.2fr;
	grid-gap: 20px;
}
input {
	background-color: #023047;
	border-color: #fefae0;
	color: #fefae0;
	padding: 10px 15px 10px 15px;
	border-radius: 15px;
	font-size: 16px;
}
button {
	background-color: #038e77;
	padding: 10px 15px 10px 15px;
	border-style: none;
	color: #fefae0;
	border-radius: 15px;
	font-size: 16px;
}
button:hover {
	cursor: pointer;
}
</style>
