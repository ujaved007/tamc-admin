<template>
	<input type="text" v-model="guard" name="guard" placeholder="enter guard's name..." />
</template>

<script>
export default {
	name: "SearchBar",
	data() {
		return {
			guard: "",
		};
	},
};
</script>

<style scope>
input {
	background-color: #023047;
	border-color: #fefae0;
	color: #fefae0;
	padding: 10px 15px 10px 15px;
	border-radius: 15px;
	font-size: 16px;
}
</style>
