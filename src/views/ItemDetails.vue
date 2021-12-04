<template>
	<v-container fluid>
		<v-row dense>
			<!-- <v-col :cols="1" :class="'pa-4'">
				<v-row v-for="i in 4" :key="i">
					<v-card class="mb-2">
						<v-img
							:src="semNome.src"
							class="white--text align-end"
							gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
							contain
						>
						</v-img>
					</v-card>
				</v-row>
			</v-col> -->
			<v-dialog
				transition="dialog-bottom-transition"
				max-width="1500"
				hide-overlay
			>
				<template v-slot:activator="{ on, attrs }">
					<v-col :cols="1" :class="'pa-4'">
						<v-row v-for="i in 4" :key="i">
							<v-card class="mb-2">
								<v-img
									v-bind="attrs"
									v-on="on"
									:src="semNome.src"
									class="white--text align-end"
									gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
									contain
								>
								</v-img>
							</v-card>
						</v-row>
					</v-col>
				</template>
				<template v-slot:default="dialog">
					<v-card>
						<v-row class="text-center">
							<v-carousel style="box-shadow: 0px 0px" hide-delimiters>
								<v-col :class="'pa-15'">
									<v-carousel-item v-for="j in 4" :key="j">
										<v-img :src="semNome.src" max-width="450"></v-img>
									</v-carousel-item>
								</v-col>
							</v-carousel>
						</v-row>
						<v-card-actions class="justify-end">
							<v-btn text @click="dialog.value = false">Close</v-btn>
						</v-card-actions>
					</v-card>
				</template>
			</v-dialog>
			<v-col :cols="6" :class="'pa-4'">
				<v-row>
					<v-card>
						<v-img
							:src="semNome.src"
							class="white--text align-end"
							gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
							contain
						>
						</v-img>
					</v-card>
				</v-row>
			</v-col>
		</v-row>
		<!-- <v-row class="text-center">
			<v-carousel style="box-shadow: 0px 0px" continuous="false">
				<v-carousel-item v-for="i in 2" :key="i">
					<v-layout row>
						<v-flex sm4 v-for="j in 6" :key="j" pl-2 pr-2>
							<v-card>
								<v-img
									src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
									aspect-ratio="0.8"
								></v-img>
								<v-card-title primary-title>
									<div>
										<h3 class="headline mb-0">Card {{ i }}-{{ j }}</h3>
										<div>Card text</div>
									</div>
								</v-card-title>
							</v-card>
						</v-flex>
					</v-layout>
				</v-carousel-item>
			</v-carousel>
		</v-row> -->
	</v-container>
	<!-- <v-card class="mx-auto pl-16" max-width="150" height="500">
		<v-container fluid>
			<v-carousel
				:cycle="true"
				height="500px"
				id="carousel"
				:hide-delimiter-background="true"
				interval="6000"
			>
				<v-carousel-item v-for="(element, i) in semNome" :key="i" :src="semNome.src">
				</v-carousel-item>
			</v-carousel>
		</v-container>
	</v-card> -->
</template>

<script>
	export default {
		name: "ItemDetails",
		props: ["item"],
		data: () => ({
			semNome: {},
		}),
		created() {
			// if you want to call it on component created
			this.semNome = JSON.parse(this.item);
		},
	};
</script>


