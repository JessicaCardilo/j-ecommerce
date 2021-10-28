<template>
	<v-card class="mx-auto pl-16" max-width="1500">
		<v-container fluid>
			<v-row class="text-center">
				<v-col cols="12">
					<h2 id="news">{{ title }}</h2>
				</v-col>
			</v-row>
			<v-row dense>
				<v-col
					v-for="(card, i) in cards"
					:key="i"
					:cols="card.flex"
					:class="card.class || 'pa-4'"
				>
					<v-card>
						<v-img
							:src="card.src"
							class="white--text align-end"
							gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
							:height="height"
						>
							<v-btn icon>
								<v-icon>mdi-heart</v-icon>
							</v-btn>
						</v-img>

						<!-- <v-card-actions> -->
						<!-- <v-card-title class="card-title" v-text="card.title"></v-card-title> -->
						<!-- <v-card-text> -->
						<!-- <v-card-title v-text="'R$' + card.price"></v-card-title> -->
						<!-- <div class="my-4 text-4">R$ {{ card.price }}</div> -->
						<!-- <div class="my-4 text-Subtitle-1"></div> -->
						<!-- <v-card-subtitle>ou 2x de R$ 12,00</v-card-subtitle> -->
						<!-- </v-card-text> -->
						<!-- </v-card-actions> -->
						<!-- <v-btn class="btn-add-to-bag">
							<v-icon> mdi-shopping-outline </v-icon>
							Adicionar à sacola
						</v-btn> -->
					</v-card>
					<div class="item-description">
						<div class="item-title">
							<span style="font-size: 18px">{{ card.title }}</span>
						</div>
						<div class="item-price">
							<h3>R$ {{ card.price }}</h3>
							<span style="font-size: 14px"
								>ou {{ card.installment }}x de R$
								{{ installmentCalc(card) }}</span
							>
						</div>
						<div class="btn-add-to-bag">
							<v-btn class="white--text" color="#41B883" width="100%">
								<v-icon> mdi-shopping-outline </v-icon>
								Adicionar à sacola
							</v-btn>
						</div>
					</div>
				</v-col>
			</v-row>
		</v-container>
	</v-card>
</template>

<script>
	export default {
		name: "Card",
		props: ["cards", "title", "height"],
		methods: {
			installmentCalc: function (card) {
				if (card.price && card.installment) {

					let nav = (card.price.replace(",", ".") / card.installment).toFixed(2);
					return nav;
				}
			},
		},
	};
</script>
<style scoped>
	#news {
		margin: 25px 0px 25px 0px;
	}
	.v-btn.v-btn--icon {
		color: #fff !important;
		float: right;
	}
	.v-card-title {
		color: gray;
	}
	.card-title {
		color: gray;
	}
	.btn-add-to-bag {
		text-align: center;
	}
	.item-description {
		margin: 20px 4px;
	}
	.item-price,
	.btn-add-to-bag {
		margin-top: 12px;
	}
</style>