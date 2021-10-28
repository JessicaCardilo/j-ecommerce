<template>
	<nav :style="{ background: background || '#333' }">
		<div class="user-area">
			<v-btn icon>
				<v-icon>mdi-account-outline</v-icon>
			</v-btn>
			<v-btn icon>
				<v-icon>mdi-heart-outline</v-icon>
			</v-btn>
			<v-btn icon>
				<v-icon>mdi-shopping-outline</v-icon>
			</v-btn>
		</div>

		<div class="search-container">
			<i class="fa fa-search"></i>
			<input
				type="search"
				placeholder="O que você está procurando?"
				name="search"
			/>
		</div>

		<ul :style="{ background: background || '#333' }" ref="nav">
			<figure class="image-logo" @click="toggleNav">
				<router-link :to="'/'">
					<img :src="imagePath" height="50px" width="50px" />
				</router-link>
			</figure>
			<li
				v-for="(link, index) in navLinks"
				:key="index"
				@mouseenter="
					$event.currentTarget.style.background = hoverBackground || '#35495E'
				"
				@mouseleave="
					$event.currentTarget.style.background = background || '#333'
				"
			>
				<router-link :to="link.path" :style="{ color: linkColor || '#fff' }">
					{{ link.text }}
				</router-link>
			</li>
		</ul>
	</nav>
</template>

<script>
	export default {
		name: "Nav",
		props: [
			"navLinks",
			"background",
			"linkColor",
			"hoverBackground",
			"imagePath",
		],
		methods: {
			toggleNav() {
				const nav = this.$refs.nav.classList;
				nav.contains("active") ? nav.remove("active") : nav.add("active");
			},
		},
	};
</script>

<style scoped lang="scss">
	nav {
		height: 92px;
		width: 100%;
		box-shadow: 2px 2px 2px #ccc;
		ul {
			display: flex;
			height: 100%;
			align-items: center;
			margin-block-start: 0;
			margin-block-end: 0;
			padding-inline-start: 0;

			figure {
				cursor: pointer;
				margin-right: 10px;
			}

			a {
				text-decoration: none;
				display: flex;
				flex-direction: row-reverse;
				align-items: center;
				font-size: 20px;
			}

			i {
				margin-right: 10px;
				font-size: 18px;
			}

			li {
				list-style-type: none;
				padding: 10px 20px;
			}
		}
		.search-container {
			float: right;
			margin: 0;
			position: relative;
			top: 50%;
			transform: translateY(-50%);
			width: 820px;
			background-color: white;
			border-radius: 32px;
			display: flex;
			align-items: center;
			padding: 12px;
			margin-right: 30px;

			input[type="search"] {
				margin-right: 28px;
				flex: 1;
				height: 20px;
				border: none;
				outline: none;
				font-size: 18px;
				padding-left: 10px;
			}

			.fa-search {
				font-size: 20px;
				color: #777;
			}
			i {
				color: #000;
				font-size: 25px;
			}
			.fa-shopping-bag {
				color: #fff;
				bottom: 1px;
				position: relative;
			}
			.shopping-bag {
				margin-left: 10px;
			}
		}
		.user-area {
			float: right;
			position: relative;
			top: 50%;
			transform: translateY(-50%);
			display: flex;
			align-items: center;
			margin-right: 90px;

			i {
				color: white;
				padding: 10px;
				font-size: 22px;
			}
		}
		.v-btn.v-btn--icon {
			color: #fff;
		}
	}

	@media screen and (max-width: 759px) {
		// tablet size
		nav {
			ul {
				position: absolute;
				width: 300px;
				flex-direction: column;
				left: -240px;
				transition: 300ms ease all;
				top: 60px;
				box-shadow: 2px 2px 2px #ccc;

				&.active {
					left: 0px;
				}

				figure {
					position: fixed;
					z-index: 1;
					top: 10px;
					left: 2px;
				}

				li {
					width: 100%;
					padding-left: 0;
					padding-right: 0;
				}

				a {
					flex-direction: row;
					margin-left: 20px;
					justify-content: space-between;
					margin-right: 13px;
				}
			}
		}
	}
</style>

