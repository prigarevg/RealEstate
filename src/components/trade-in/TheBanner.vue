<template>
	<section class="banner">
		<div class="banner__container center">
			<div
				class="banner__description animate__animated animate__fadeInLeft wow"
			>
				<h1 class="banner__title">Trade-in</h1>
				<h3 class="banner__subtitle">
					Trade-in — это программа, которая поможет обменять вашу
					старую квартиру на новую
				</h3>
				<v-button
					:text="'Оформить заявку'"
					:type="'button'"
					class="blue"
				></v-button>
			</div>
			<div class="banner__img animate__animated animate__fadeInRight wow">
				<img src="img/trade-in/img.svg" alt="" />
			</div>
			<div class="banner__footer animate__animated animate__fadeInUp wow">
				<div class="banner__info">
					<h4
						class="banner__info-title animate__animated animate__fadeInUp wow"
					>
						Услуга страхования
					</h4>
					<h5
						class="banner__info-subtitle animate__animated animate__fadeInUp wow"
					>
						Финансовая защита всех<br />
						участников сделки
					</h5>
				</div>
				<div class="banner__info">
					<h4
						class="banner__info-title animate__animated animate__fadeInUp wow"
					>
						Независимая оценка жилья
					</h4>
					<h5
						class="banner__info-subtitle animate__animated animate__fadeInUp wow"
					>
						Финансовая защита всех<br />
						участников сделки
					</h5>
				</div>
				<div class="banner__info">
					<h4
						class="banner__info-title animate__animated animate__fadeInUp wow"
					>
						Собираем документы
					</h4>
					<h5
						class="banner__info-subtitle animate__animated animate__fadeInUp wow"
					>
						Финансовая защита всех<br />
						участников сделки
					</h5>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
	import VButton from "../general/v-button.vue";

	export default {
		name: "Banner",
		components: {
			VButton,
		},
	};
</script>

<style lang="scss" scoped>
	.banner {
		background: linear-gradient(
			0deg,
			rgba(255, 255, 255, 0) 0%,
			rgba(237, 245, 253, 1) 10%
		);
		min-height: calc(100vh - 6rem);
		display: flex;

		align-items: center;
		&__container {
			display: grid;
			grid-column-gap: 15rem;
			grid-row-gap: 9rem;
			grid-template-columns: repeat(2, 1fr);
			height: fit-content;
		}
		&__description {
			display: flex;
			flex-direction: column;
			.button {
				min-width: 24rem;
				margin-top: auto;
			}
		}
		&__title {
			font-size: var(--text-80);
			font-weight: 600;
			color: var(--blue);
			margin: 5rem 0 5rem 0;
		}
		&__subtitle {
			font-size: var(--text-28);
			line-height: 3.5rem;
			color: #6f6f6f;
			max-width: 58rem;
		}
		&__img {
			min-height: 42rem;
		}
		&__footer {
			display: flex;
			justify-content: space-between;
			gap: 2rem;
			grid-area: 2/1/2/3;
			background-color: var(--white);
			border-radius: 3rem;
			padding: 4.4rem 9rem 5rem 9rem;
			box-shadow: 0 0 2rem rgba(0, 0, 0, 0.2);
		}
		&__info {
			text-align: center;
			&-title {
				color: var(--blue);
				font-weight: 600;
				font-size: var(--text-25);
				margin-bottom: 1.5rem;
			}
			&-subtitle {
				color: var(--dark);
				font-size: var(--text-18);
				line-height: 2.2rem;
			}
		}
	}
</style>
