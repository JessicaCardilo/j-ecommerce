<template>
	<div>
		<div class="carrousel">
			<Carousel />
		</div>
		<div class="news">
			<Card :cards="news" :title="'Novidades'" :height="350"/>
		</div>
		<div class="shoes">
			<Card :cards="shoes" :title="'Calçados'" :height="350"/>
		</div>
	</div>
</template>

<script>
	import Carousel from "../components/Carousel.vue";
	import Card from "../components/Card.vue";

	export default {
		name: "Home",
		components: {
			Carousel,
			Card,
		},
		
		data: () => ({
			news: [
				{
					title: "Lorem ipsum",
					src: "https://ae01.alicdn.com/kf/H01f820315a5c45a185536f88433239deJ/Camiseta-feminina-com-um-humor-complicado-camiseta-para-meninas-veganos-pode-fazer-algo-roupa-para-o.png",
					flex: 3,
					price: "24,00",
					installment: 2,
				},
				{
					title: "Ut ac porta ex",
					src: "https://www.hypeness.com.br/1/2015/07/modavegan12.jpg",
					flex: 3,
					price: "40,00",
					installment: 2,
				},
				{
					title: "Donec feugiat",
					src: "https://images.tcdn.com.br/img/img_prod/572623/camisa_listrada_elephunk_unissex_stripz_rumba_rosa_1369_2_20200127023758.jpg",
					flex: 3,
					price: "115,00",
					installment: 2,
				},
				{
					title: "Proin lacinia",
					src: "https://i.pinimg.com/originals/b7/dd/61/b7dd6127f6e5b87960bb24dea3a34ae1.jpg",
					flex: 3,
					price: "22,90",
					installment: 2,
				},
				{
					title: "Aenean",
					src: "https://cdn.shopify.com/s/files/1/0892/7618/products/12x16-vegan-modern-02_mockup_Wrinkle-Front_Grey-Triblend_2048x.png?v=1599158412",
					flex: 3,
					price: "17,90",
					installment: 2,
				},
				{
					title: "Morbi in",
					src: "https://ng.jumia.is/unsafe/fit-in/680x680/filters:fill(white)/product/76/082414/1.jpg?9052",
					flex: 3,
					price: "140,00",
					installment: 2,
				},
				{
					title: "Nam risus",
					src: "https://img.elo7.com.br/product/original/2AD3216/body-bebe-roupa-nene-dinossauros-carnivoro-vegetariano-vegan-marcas.jpg",
					flex: 3,
					price: "117,95",
					installment: 2,
				},
				{
					title: "Nulla auctor",
					src: "https://cea.vtexassets.com/arquivos/ids/15335250/Camisa-Unissex-Estampada-Xadrez-em-Flanela-com-Bolso-Manga-Longa-Verde-9809541-Verde_1.jpg?v=637323214065430000",
					flex: 3,
					price: "30,00",
					installment: 2,
				},
			],
			shoes: [
				{
					title: "Pre-fab homes",
					src: "https://images.tcdn.com.br/img/img_prod/707677/tenis_vegano_shoes_street_bege_983_1_e094a4b6c410ae9b79242a93dcb31e56.jpg",
					flex: 3,
					price: "165,90",
					installment: 2,
				},
				{
					title: "Pre-fab homes",
					src: "https://images.tcdn.com.br/img/img_prod/707677/bota_vegano_shoes_naturale_soft_aspargo_965_1_6ff537c4d9e113e1d279c3b2b5f52c2f.jpg",
					flex: 3,
					price: "215,95",
					installment: 3,
				},
				{
					title: "Pre-fab homes",
					src: "https://i1.wp.com/www.canalmasculino.com.br/wp-content/uploads/2017/10/sapatos-veganos-masculinos-vegano-shoes-loafer-570x401.jpg?resize=570%2C401",
					flex: 3,
					price: "255,20",
					installment: 3,
				},
				{
					title: "Pre-fab homes",
					src: "https://vegazeta.com.br/wp-content/uploads/2020/10/nothing-new-plastic-low-top-shoes-3-768x768-1.jpg",
					flex: 3,
					price: "99,90",
					installment: 2,
				},
				{
					title: "Pre-fab homes",
					src: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT-NMGILpu9XnRThvMvDDN0QLRwFd7x3tZ05Q&usqp=CAU",
					flex: 3,
					price: "99,00",
					installment: 2,
				},
				{
					title: "Pre-fab homes",
					src: "https://img.elo7.com.br/product/original/2290B26/sapatilha-vegana-verde-calcados-veganos.jpg",
					flex: 3,
					price: "75,00",
					installment: 2,
				},
				{
					title: "Pre-fab homes",
					src: "https://images.tcdn.com.br/img/img_prod/707677/tenis_vegano_shoes_strong_boost_vegan_verde_1089_1_c450f93b0825cdb10458fb7cedd4dfe9.jpg",
					flex: 3,
					price: "120,00",
					installment: 2,
				},
				{
					title: "Pre-fab homes",
					src: "https://cdn.shopify.com/s/files/1/0127/3711/8265/files/vt146-tenis-vert-wata-white-natural-sole-11862_large.jpg?v=1536269219",
					flex: 3,
					price: "100,00",
					installment: 2,
				},
			],
		}),
	};
</script>
