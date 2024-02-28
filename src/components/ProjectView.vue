<template>
	<section id="project">
		<div class="project_container">
			<div class="project_title">
				<h3>project</h3>
				<div class="line"></div>
			</div>

			<div class="project_main">
				<article class="project_content" v-for="(port, index) in projectInfo" :key="index">
					<span>{{ index + 1 }}.</span>
					<div class="project_info">
						<img :src="port.imgURL" :alt="port.imgAlt" />
						<div class="info_box">
							<p class="project_mainText">{{ port.mainText }}</p>
							<p class="project_subText">{{ port.subText }}</p>
							<div class="project_btn_box">
								<base-button :href="port.siteURL">site view</base-button>
								<base-button :href="port.gitURL">github view</base-button>
							</div>
						</div>
					</div>
				</article>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	data() {
		return {
			projectInfo: [
				{
					imgURL: '/images/vueProject1.png',
					imgAlt: '뷰 프로젝트',
					mainText: "낙시고-낚시 예약 사이트",
					subText: "저의 취미를 살려서 낚시 예약 사이트를 제작하였습니다.<br> vue.js를 이용하여 제작하였으며 다양한 API를 사용하였습니다. <br> 로그인, 선박등록, 예약 기능을 사용할 수 있습니다.",
					siteURL: "https://fishing-reservation-54646.web.app",
					gitURL: "https://github.com/kdh990315/fishing-reservation.git",
				},
				{
					imgURL: '/images/MileProject.png',
					imgAlt: '밀리의서재 프로젝트',
					mainText: "Millie Library",
					subText: "밀리의 서재를 클론코딩하였습니다. ajex로 통해 kakao API를 가져와 사용했습니다.",
					siteURL: "https://kdh990315.github.io/project06_ajax/",
					gitURL: "https://github.com/kdh990315/project06_ajax.git",

				},
				{
					imgURL: '/images/basicProject.png',
					imgAlt: 'Baice Site',
					mainText: "가장 기본적인 사이트",
					subText: "가장 기본적인 레이아웃과 기능들을 사용하여 작업하였습니다.",
					siteURL: "https://kdh990315.github.io/basic-site/",
					gitURL: "https://github.com/kdh990315/basic-site.git",

				},
				{
					imgURL: '/images/react_img.png',
					imgAlt: '리액트 프로젝트',
					mainText: "React Site",
					subText: "넥슨 OPEN API를 사용하여 프로잭트를 제작중에 있습니다. 버튼을 누르시면 현재 제작하고 있는 웹사이트를 확인해보실 수 있습니다.",
					siteURL: "#",
					gitURL: "#",

				},
			],
		}
	}
}
</script>

<style lang="scss" scoped>
@import '@/scss/mixin.scss';

.project_container {
	max-width: 80%;
	margin: 0 auto 0 15%;
	margin-top: 300px;

	.project_title {
		position: sticky;
		top: 130px;
		padding-bottom: 25px;

		h3 {
			@include title-text;
		}

		.line {
			width: 35%;
			height: 2px;
			background-color: #fff;
			border-radius: 50%;
		}
	}

	.project_main {
		.project_content {
			width: 100%;
			padding-bottom: 50px;
			position: sticky;


			span {
				font-size: 5vw;
				font-weight: 900;
				padding-left: 30px;

				@media (max-width: 1500px) {
					font-size: 3vw;
					padding-left: 10px;
				}
			}

			.project_info {
				position: sticky;

				@include c-center;

				img {
					width: 600px;
					height: 400px;
					margin-bottom: 15px;
					border-radius: 20px;
				}

				.info_box {
					width: 400px;
					margin-left: 100px;

					p {
						color: black;
						text-align: left;
					}

					.project_mainText {
						font-size: 1.96rem;
						font-weight: 900;
						padding: 5px 0;
						text-align: left;
						margin-bottom: 15px;
					}

					.project_subText {
						font-size: 1.15rem;
						padding-top: 5px;
						text-align: left;
						line-height: 24px;
					}

					.project_btn_box {
						margin-top: 50px;
					}
				}

				@media (max-width: 1500px) {
					justify-content: space-around;

					img {
						width: 500px;
						height: 300px;
					}
					.info_box {
						width: 300px;
						margin-left: 0;

						.project_mainText {
							font-size: 1.65rem;
						}

						.project_subText {
							font-size: 1.05rem;
						}
					}
				}

				@media (max-width: 1200px) {
					flex-direction: column;
				}

				@media (max-width: 768px) {
					img {
						width: calc(100% - 100px);
					}
				}

				@media (max-width: 500px) {
					display: flex;
					align-items: center;
					justify-content: center;
					flex-direction: column;

					img {
						width: 300px;
						height: 200px;
					}

					.info_box {
						margin-left: 0;

						.project_mainText {
							font-size: 1.36rem;
							text-align: center;
						}

						.project_subText {
							font-size: .95rem;
						}

						.project_btn_box {
							width: 100%;
							display: flex;
							justify-content: space-evenly;
						}
					}
				}
			}

			&:nth-of-type(1) {
				background-color: #ffe4c4;
				top: 255px;

				@media (max-width: 800px) {
					top: 193px;
				}
			}

			&:nth-of-type(2) {
				background-color: #e7ceb0;
				top: 275px;

				@media (max-width: 800px) {
					top: 213px;
				}
			}

			&:nth-of-type(3) {
				background-color: #c5b095;
				top: 295px;

				@media (max-width: 800px) {
					top: 233px;
				}
			}

			&:nth-of-type(4) {
				background-color: #8f806e;
				top: 315px;

				@media (max-width: 800px) {
					top: 253px;
				}
			}
		}
	}

	@media (max-width: 800px) {
		width: 100%;
		margin: 150px auto 0 auto;
	}
}
</style>