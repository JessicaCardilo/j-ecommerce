<template>
	<v-footer class="footer" color="#419584" height="100px" elevation="24">
		<strong class="subheading" style="color: #fff"
			>Lorem Ipsum is simply dummy text of the printing and typesetting industry.</strong
		>

		<v-spacer></v-spacer>

		<v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
			<v-icon size="24px">
				{{ icon }}
			</v-icon>
		</v-btn>
	</v-footer>
</template>
<script>
	export default {
		name: "Footer",
		data: () => ({
			icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
		}),
	};
</script>
<style scoped>
	.footer {
		margin-top: 30px;
	}
</style>