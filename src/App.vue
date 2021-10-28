<template>
	<v-app>
		<Nav
			:navLinks="navLinks"
			:background="'#419584'"
			:imagePath="require('./assets/logo.png')"
			:hoverBackground="''"
			:linkColor="'#fff'"
		/>
		<Bar
			:barLinks="barLinks"
			:background="'#fff'"
			:barColor="'#000'"
			:hoverBackground="'#41B883'"
		/>

		<v-main>
			<router-view />
		</v-main>
		<Footer />
	</v-app>
</template>

<script>
	import Nav from "./components/Nav.vue";
	import Bar from "./components/Bar.vue";
	import Footer from "./components/Footer.vue";

	export default {
		name: "App",
		components: {
			Nav,
			Bar,
			Footer,
		},
		data: () => ({
			navLinks: [
				{
					text: "Sobre",
					path: "/about",
					icon: "",
				},
				{
					text: "Contato",
					path: "/Contact",
					icon: "",
				},				
			],
			barLinks: [
				{
					text: "Novidades",
					path: "/Novelty",
					icon: "",
				},
				{
					text: "Infantil",
					path: "/Childrens",
					icon: "",
				},
				{
					text: "Moda íntima",
					path: "/Underwear",
					icon: "",
				},
				{
					text: "Calçados",
					path: "/Shoes",
					icon: "",
				},
				{
					text: "Acessórios",
					path: "/Props",
					icon: "",
				},
				{
					text: "Cuidados",
					path: "/Care",
					icon: "",
				},
				{
					text: "Perfumaria",
					path: "/Perfumery",
					icon: "",
				},
				{
					text: "Livraria",
					path: "/Bookstore",
					icon: "",
				},
			],
		}),
	};
</script>
