<template>
	<nav :style="{ background: background || '#333' }">
		<ul :style="{ background: background || '#333' }" ref="nav">
			<li
				v-for="(bar, index) in barLinks"
				:key="index"
				@mouseenter="
					$event.currentTarget.style.background = hoverBackground || '#35495E'
				"
				@mouseleave="
					$event.currentTarget.style.background = background || '#333'
				"
			>
				<router-link :to="bar.path" :style="{ color: barColor || '#fff' }">
					{{ bar.text }}
					<i :class="bar.icon" />
				</router-link>
			</li>
		</ul>
	</nav>
</template>

<script>
	export default {
		name: "Bar",
		props: ["barLinks", "background", "barColor", "hoverBackground"],
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
		height: 45px;
		width: 100%;
		box-shadow: 2px 2px 2px #ccc;
		ul {
			display: flex;
			height: 100%;
			align-items: center;
			margin-block-start: 0;
			margin-block-end: 0;
			padding-inline-start: 0;
			justify-content: center;

			figure {
				cursor: pointer;
				margin-right: 10px;
			}

			a {
				text-decoration: none;
				display: flex;
				flex-direction: row-reverse;
				align-items: center;
				font-size: 16px;
				font-weight: bold;
			}

			i {
				margin-right: 10px;
				font-size: 12px;
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
			-ms-transform: translateY(-50%);
			transform: translateY(-50%);
			width: 255px;
			height: 15px;
			background-color: white;
			border-radius: 32px;
			display: flex;
			align-items: center;
			padding: 12px;
			margin-right: 90px;
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
			.fa-shopping-bag {
				color: #fff;
				bottom: 1px;

				font-size: 25px;
				position: relative;
			}
			.shopping-bag {
				margin-left: 10px;
			}
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

