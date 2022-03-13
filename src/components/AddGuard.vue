<template>
	<form action="">
		<SearchBar />
		<Button text="Add" />
	</form>
</template>

<script>
import SearchBar from "./SearchBar.vue";
import Button from "./Button.vue";

export default {
	name: "AddGuard",
	components: {
		SearchBar,
		Button,
	},
};
</script>

<style scope>
form {
	display: grid;
	grid-template-columns: 1fr 0.2fr;
	grid-gap: 20px;
}
</style>
