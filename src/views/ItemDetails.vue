<template>
	<div>
		<span>Item details {{ semNome.title }}</span>
	</div>
</template>

<script>
	export default {
		name: "ItemDetails",
		props: ["item"],
		data: () => ({
			semNome: {}
		}),
		created() {
			// if you want to call it on component created
			this.semNome = JSON.parse(this.item);
		},
	};
</script>


