<template>
	<a
		to
		class="catalog__item animate__animated animate__fadeInUp wow"
		data-wow-duration="1s"
		v-for="item in items"
		:key="item.id"
		:href="item.address"
	>
		<img :src="item.img" alt="" />
		<div class="catalog__item-tags">
			<div
				class="catalog__item-tag"
				:style="item.style"
				v-for="tag in item.tags"
				:key="tag.id"
			>
				{{ tag.tag }}
			</div>
		</div>
		<div class="catalog__item-name">
			<h3>{{ item.type }}</h3>
			<h4>{{ item.title }}</h4>
		</div>
	</a>
</template>

<script>
	export default {
		name: "CatalogItem",
		props: {},
		data() {
			return {
				items: [
					{
						id: 1,
						img: `img/general/catalog-item1.png`,
						tags: [
							{
								id: 1,
								tag: "Волгоград",
							},
							{
								id: 2,
								tag: "Бизнес-класс",
							},
							{
								id: 3,
								tag: "Ворошиловский район",
							},
						],
						style: `background-color: var(--white); color: var(--blue);`,
						type: "Жилой комплекс",
						title: "Dolce vita",
						address: "#",
					},
					{
						id: 2,
						img: `img/general/catalog-item2.png`,
						tags: [
							{
								id: 1,
								tag: "Волгоград",
							},
							{
								id: 2,
								tag: "Комфорт-класс",
							},
							{
								id: 3,
								tag: "Ворошиловский район",
							},
						],
						style: `background-color: var(--light-blue); color: var(--white);`,
						type: "Клубный дом",
						title: "Академический",
						address: "#/academ",
					},
					{
						id: 3,
						img: `img/general/catalog-item3.png`,
						tags: [
							{
								id: 1,
								tag: "Ахтубинск",
							},
							{
								id: 2,
								tag: "Комфорт-класс",
							},
							{
								id: 3,
								tag: "Уникальное фасадное решение",
							},
							{
								id: 4,
								tag: "Огороженная территория",
							},
						],
						style: `background-color: var(--white); color: var(--blue);`,
						type: "Жилой комплекс",
						title: "Андреевский",
						address: "#",
					},
					{
						id: 4,
						img: `img/general/catalog-item4.png`,
						address: "#",
					},
				],
			};
		},
		methods: {
			setTagsPosition() {
				const tags = document.querySelector(".catalog__item-tags");
				tags.classList.add("right");
			},
			setNamePosition() {
				const name = document.querySelectorAll(".catalog__item-name");
				name[2].classList.add("left");
			},
		},
		mounted() {
			this.setTagsPosition();
			this.setNamePosition();
		},
	};
</script>

<style lang="scss" scoped>
	.catalog__item {
		display: block;
		position: relative;
		border-radius: 2.5rem;
		padding: 2rem;
		overflow: hidden;
		height: 49rem;

		img {
			position: absolute;
			left: 0;
			top: 0;
			height: 100%;
			width: 100%;
			object-fit: cover;
			z-index: -1;
		}
		&-tags {
			position: absolute;
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
			align-items: center;
			gap: 0.5rem;
			width: 27.7rem;
			top: 2rem;
			left: 2rem;

			&.right {
				left: inherit;
				right: 2rem;
			}
		}
		&-tag {
			display: inline-block;
			min-width: 13.6rem;
			padding: 0.8rem 1rem;
			font-size: var(--text-14);
			font-weight: 600;
			text-align: center;
			border-radius: 2rem;
			&:nth-child(n + 3) {
				width: 100%;
			}
		}
		&-name {
			position: absolute;
			bottom: 2rem;
			right: 2rem;
			&.left {
				right: inherit;
				left: 2rem;
			}
			h3,
			h4 {
				font-weight: 800;
				color: var(--white);
			}
			h3 {
				font-size: var(--text-24);
			}
			h4 {
				font-size: var(--text-36);
				text-transform: uppercase;
				text-align: center;
			}
		}
	}
</style>
