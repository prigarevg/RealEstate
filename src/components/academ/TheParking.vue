<template>
	<section class="parking" id="parking">
		<div class="parking__container center">
			<figure class="parking__img">
				<img src="img/academ/advantage-img2.png" alt="" />
			</figure>
			<div class="parking__content">
				<h2>
					и о погоде… <br />
					погода у нас <br />
					хорошая
				</h2>
				<p>
					Вам больше не придётся счищать с крыши вашего автомобиля
					свежевыпавший снежок или усердно протирать лобовое стекло от
					следов ночного дождя и пыльной бури.
				</p>

				<p>
					Вы просто спускаетесь на лифте в подземный паркинг, заводите
					мотор и спокойно едете по своим делам.
				</p>
				<p>
					А вернувшись вечером домой, открываете багажник, достаёте
					покупки и поднимаетесь на лифте на свой этаж.
				</p>

				<p>
					Лифт, кстати, грузовой, в нём при необходимости поместится и
					шкаф для кухни, и громоздкая ванна.
				</p>
			</div>
		</div>
		<div class="parking__footer">
			<div class="parking__container center">
				<div></div>
				<div class="parking__footer-bottom">
					<academ-button
						:text="'Забронировать место'"
						:type="'button'"
						class="gold"
					></academ-button>
					<div @click="openPopup()">
						<img src="img/academ/parking.svg" alt="" />
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
	import AcademButton from "./academ-button.vue";

	export default {
		name: "Parking",
		components: {
			AcademButton,
		},
		methods: {
			openPopup() {
				const popup = document.querySelector(".popup");
				const popupImage = popup.querySelector(".popup__image");
				popupImage.setAttribute("src", "img/academ/parking.svg");
				document
					.querySelector("body")
					.setAttribute("style", "overflow: hidden");
				popup.classList.add("open");
			},
		},
	};
</script>

<style lang="scss" scoped>
	.parking {
		display: block;
		padding: 0;
		&__container {
			display: grid;
			grid-gap: 4rem;
			grid-template-columns: 1fr 53rem;
		}
		&__img {
			max-height: 63rem;
			img {
				transform: translateX(-25%);
				width: 130%;
				height: 100%;
			}
		}
		&__content {
			h2 {
				text-transform: uppercase;
				font-size: 4.8rem;
				color: var(--gold);
				font-weight: 300;
				margin-bottom: 5rem;
			}
			p {
				color: var(--white);
				font-size: 1.8rem;
				line-height: 2.2rem;
			}
			p + p {
				margin-top: 3rem;
			}
			p:last-child {
				padding-bottom: 3rem;
			}
		}
		&__footer {
			min-height: 38rem;
			background: url(/img/academ/reserve-seat.png) center / cover
				no-repeat;
			.parking__container {
				div {
					margin-top: 1.5rem;
					display: flex;
					align-items: center;
					gap: 10rem;
				}
			}
			&-bottom {
				div {
					cursor: pointer !important;
					img {
						width: 20rem;
					}
				}
			}
		}
	}
</style>
