<template>
	<section class="office" id="office">
		<div class="office__left">
			<div class="office__feature">
				<p class="office__feature-word">ቢሮ</p>
				<p class="office__feature-description">
					А вот так пишется «ОФИС»<br />
					на ахмарском языке.
				</p>
			</div>
		</div>
		<div class="office__right">
			<div class="office__right-container">
				<div class="office__title">
					<img
						src="img/icon/academ/semicircle.svg"
						class="office__semicircle"
						alt=""
					/>
					<img
						src="img/icon/academ/office.svg"
						class="office__text"
						alt=""
					/>
				</div>
				<img
					src="img/academ/office-img.png"
					class="office__img"
					alt=""
				/>
				<academ-button
					:text="'Выбрать офис'"
					:type="'button'"
					class="gold"
				></academ-button>
				<div class="office__schemes">
					<div @click="openPopup(1)">
						<img src="img/academ/office1.svg" alt="" />
					</div>
					<div @click="openPopup(2)">
						<img src="img/academ/office2.svg" alt="" />
					</div>
				</div>
			</div>
		</div>
		<popup />
	</section>
</template>

<script>
	import AcademButton from "./academ-button.vue";
	import Popup from "./Popup.vue";

	export default {
		name: "Office",
		components: {
			AcademButton,
			Popup,
		},
		methods: {
			openPopup(imageNumber) {
				const popup = document.querySelector(".popup");
				const popupImage = popup.querySelector(".popup__image");
				document
					.querySelector("body")
					.setAttribute("style", "overflow: hidden");
				popup.classList.add("open");

				switch (imageNumber) {
					case 1: {
						popupImage.setAttribute(
							"src",
							"img/academ/office1.svg"
						);
						break;
					}
					case 2: {
						popupImage.setAttribute(
							"src",
							"img/academ/office2.svg"
						);
						break;
					}
					default: {
						break;
					}
				}
			},
		},
	};
</script>

<style lang="scss" scoped>
	.office {
		padding: 0;
		display: grid;
		grid-template-columns: 34% 66%;
		&__left {
			position: relative;
			background: url("/img/academ/office-bg1.png") center / cover
				no-repeat;
		}
		&__feature {
			position: absolute;
			bottom: 3rem;
			right: 2.5rem;
			display: flex;
			align-items: center;
			gap: 2rem;
			&-word {
				font-size: 5rem;
				font-weight: 100;
			}
			&-description {
				color: var(--dark-green);
				font-size: var(--text-13);
				font-weight: 600;
			}
		}
		&__right {
			background: url("/img/academ/office-bg2.png") center / cover
				no-repeat;
			display: flex;
			align-items: center;
			padding: 1.5rem 0;
			&-container {
				height: fit-content;
			}
		}
		&__title {
			position: relative;
			margin-bottom: 7rem;
		}
		&__semicircle {
			position: absolute;
			top: 50%;
			left: 0;
			height: 25rem;
			transform: translateY(-50%) rotate(180deg);
		}
		&__text {
			position: relative;
			left: -10.5rem;
		}
		&__img {
			margin-bottom: 4.5rem;
		}
		.button {
			min-width: 18rem;
			width: min-content;
			margin-bottom: 4.5rem;
		}
		&__schemes {
			display: flex;
			gap: 1rem;
			div {
				cursor: pointer;
			}
			img {
				cursor: pointer;
				height: 12rem;
			}
			margin-bottom: 1rem;
		}
	}
</style>
