<template>
	<v-carousel
		:cycle="true"
		height="800px"
		id="carousel"
		:hide-delimiter-background="true"
		interval="6000"
	>
		<v-carousel-item v-for="(item, i) in items" :key="i" :src="item.src">
		</v-carousel-item>
	</v-carousel>
</template>

<script>
	import imageStylishElegant from "@/assets/Carousel/stylish-elegant.jpg";

	export default {
		name: "Carousel",
		data() {
			return {
				items: [
					{
						title: "Go Vegan",
						src: "https://veganbusiness.com.br/wp-content/uploads/2019/02/comprar-roupas-veganas.jpg",
					},
					{
						title: "Go Vegan",
						src: "https://ssl8972.websiteseguro.com/curtiram/images/fotos/mh_interna_destaque_marcarvegan-4.png",
					},
					{
						title: "Go Vegan",
						src: imageStylishElegant,
					},
					{
						title: "Go Vegan",
						src: "https://casadasustentabilidade.files.wordpress.com/2016/09/roupa-sustentc3a1vel-baby-vegano-1.jpg?w=1200",
					},
					{
						title: "Go Vegan",
						src: "https://peritavegana.com/wp-content/uploads/2019/12/2019-12-06-1-680x261.png",
					},
				],
			};
		},
	};
</script>