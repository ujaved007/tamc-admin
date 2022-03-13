<template>
	<div class="card">
		<h1>TAMC Extension Admin</h1>
		<h3>Manage Guard Names</h3>
		<AddGuard />
		<p class="p-sm-italic">
			Please enter name exactly as it appears in the TAMC portal otherwise extension won’t be able to autofill it.
		</p>
	</div>
</template>

<script>
import AddGuard from "./AddGuard.vue";

export default {
	name: "CardHeader",
	components: { AddGuard },
};
</script>

<style>
.p-sm-italic {
	font-size: 14px;
	font-style: italic;
	line-height: 20px;
}
</style>
