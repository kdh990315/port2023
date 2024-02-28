<template>
	<section id="script">
		<div class="script_container">
			<div class="script_title">
				<h3>script</h3>
				<p>작업물</p>
				<div class="script_line"></div>
			</div>
			<article class="script_contents">
				<div class="contents" v-for="(content, index) in scrpitContents" :key="index" :class="`content${index + 1}`">
					<div class="contents_left">
						<div class="script_view">
							<video :src="content.src" autoplay loop muted playsinline></video>
						</div>
					</div>
					<div class="contents_right">
						<p class="num">{{ index + 1 }}.</p>
						<div class="line"></div>
						<h4>{{ content.title }}</h4>
						<p>{{ content.subText }}</p>
					</div>
				</div>
			</article>
		</div>
	</section>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
	mounted: function () {
		this.scrollAnimation();

	},
	data() {
		return {
			scrpitContents: [
				{
					src: "/video/background_star.mp4",
					title: "Star Background",
					subText: "Javascript를 이용하여 배경에 별이 반짝거리는 느낌을 연출하였습니다.",
				},
				{
					src: "/video/glitch.mp4",
					title: "Glitch Efect",
					subText: "Javascript를 이용하여 텍스트가 버퍼링이나 지지직거리는 느낌을 연출하는 glitch효과를 연출하였습니다.",
				},
				{
					src: "/video/infinite_slide.mp4",
					title: "Infinite Slide Efect",
					subText: "Javascript를 이용하여 기본 Slide효과에서 더욱 업그레이드된 무한슬라이드를 만들었습니다.",
				},
				{
					src: "/video/tetrisgame.mp4",
					title: "Tetris Game",
					subText: "Javascript를 이용하여 테트리스 게임을 만들었습니다.",
				},
				// {
				// 	src: "#",
				// 	title: "title dummy text",
				// 	subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
				// },
				// {
				// 	src: "#",
				// 	title: "title dummy text",
				// 	subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
				// },
				// {
				// 	src: "#",
				// 	title: "title dummy text",
				// 	subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
				// },
				// {
				// 	src: "#",
				// 	title: "title dummy text",
				// 	subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
				// },
				// {
				// 	src: "#",
				// 	title: "title dummy text",
				// 	subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
				// },
				// {
				// 	src: "#",
				// 	title: "title dummy text",
				// 	subText: "sub 더미 택스트입니다.sub 더미 택스트입니다.sub 더미 택스트입니다.",
				// },
			]
		}
	},

	methods: {
		scrollAnimation() {
			const contents = gsap.utils.toArray(".contents");

			ScrollTrigger.matchMedia({
				"(min-width: 800px)": function () {
					gsap.to(contents, {
						xPercent: -160 * (contents.length - 1),
						ease: "none",
						scrollTrigger: {
							trigger: "#script",
							start: "top 130px",
							end: "+=12000",
							pin: true,
							scrub: 1,
							markers: false,
							invalidateOnRefresh: true,
							anticipatePin: 1,
						}
					});
				},
				"(max-width: 768px)": function () {
					gsap.to(contents, {
						xPercent: -165 * (contents.length - 1),
						ease: "none",
						scrollTrigger: {
							trigger: "#script",
							start: "top 130px",
							end: "+=5000",
							pin: true,
							scrub: 1,
							markers: false,
							invalidateOnRefresh: true,
							anticipatePin: 1,
						}
					});
				},
			})
		}
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

#script {
	width: 100%;
	height: 30vh;
	margin-top: 300px;

	.script_container {
		max-width: 80%;
		margin: 0 auto 0 15%;

		.script_title {
			color: #fff;
			width: 100%;

			h3 {
				font-size: 5vw;
				font-weight: bold;
				text-transform: uppercase;
				display: inline-block;
				font-family: 'Poppins', sans-serif;
			}

			p {
				font-size: 1vw;
				font-weight: 400;
				display: inline-block;
				margin-left: 20px;
			}

			.script_line {
				width: 55%;
				height: 2px;
				background-color: #fff;
				border-radius: 50%;
			}
		}

		.script_contents {
			width: 16080px;
			display: flex;
			flex-wrap: wrap;
			z-index: 10;

			.contents {
				@include center-se;
				width: 1500px;
				height: 650px;
				margin: 30px 120px 0 0;
				border-radius: 100px;

				&:last-child {
					margin: 30px 0 0 0;
				}

				&.content1 {
					background-color: #36454F;
				}

				&.content2 {
					background-color: #4F5357;
				}

				&.content3 {
					background-color: #3F4E57;
				}
				&.content4 {
					background-color: #425358;
				}
				&.content5 {
					background-color: #475357;
				}
				&.content6 {
					background-color: #3F4A4F;
				}
				&.content7 {
					background-color: #4C5358;
				}
				&.content8 {
					background-color: #4A5357;
				}
				&.content9 {
					background-color: #3E4E57;
				}
				&.content10 {
					background-color: #3D4F53;
				}


				.contents_left {
					width: 50%;
					padding: 30px 0;
					@include center;

					.script_view {
						width: 700px;

						video {
							width: 90%;
							border-radius: 50px;
						}
					}
				}

				.contents_right {
					width: 40%;

					.num {
						font-size: 3vw;
						font-weight: 900;
					}

					.line {
						width: 100%;
						height: 5px;
						background-color: #fff;
						margin-bottom: 20px;
					}

					h4 {
						font-size: 3vw;
						font-weight: 600;
						font-family: "Poppins", sans-serif;
						margin-top: 35px;
						margin-bottom: 50px;
					}

					p {
						font-size: 1rem;
						font-weight: 400;
						line-height: 1.8;
					}
				}
			}
		}
	}

	@media (max-width: 768px) {

		.script_container {
			margin: 0 auto;

			.script_contents {

				.contents {
					width: 500px;
					text-align: center;
					padding-bottom: 30px;
					border-radius: 20px;
					@include c-center;
					flex-direction: column;
					.contents_left {
						width: 100%;
						.script_view {
							width: 400px;

							video {
								width: 100%;
							}
						}
					}

					.contents_right {
						width: 100%;

						.num {
							font-size: 2.5rem;
						}

						h4 {
							font-size: 2.5rem;
						}

						.line {
							width: 65%;
							margin: 0 auto 30px auto;
						}
					}
				}

			}
		}


	}
}
</style>