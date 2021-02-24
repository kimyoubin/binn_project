<template>
	<div class="tab02-sec01">
		<section-title secType="tab02-sec01">이벤트 참여 방법</section-title>

		<div class="wrap">
			<tab-02-section-01-list> 
				아래 목록에서<br>한우인증점을 클릭하여<br>인증점에 대한 내용을<br>확인해주세요.
			</tab-02-section-01-list>
			<tab-02-section-01-list 
				listNum="list02"> 
				마음에 드는<br>최애 한우인증점에<br>이유를 적고, 좋아요 댓글을<br>남겨주세요.
			</tab-02-section-01-list>
			<tab-02-section-01-list 
				listNum="list03"> 
				이벤트 응모 완료!<br>하루 1회 참여로<br>당첨 확률을 높여보세요.
			</tab-02-section-01-list>			
		</div>	

		<vue-tab areaType="area-tab"></vue-tab>

		<div class="wrap thumb-list">
			<tab-02-section-01-thumb-list
				:items="thumbList"
				@click="modalOn">
			</tab-02-section-01-thumb-list>
		</div>

		<bg-type-button 
            width="360px"
            height="63px"
            funcType="btn-more">인증점 더보기</bg-type-button>
		
		<!-- step01 -->
		<vue-modal
			colorType="modal-pink"
			padding="pd50"
			v-show="step01Modal"
			:activeInfo="activeInfo"
			@close="close">
            <template slot="title">내 마음 속의 <i class="point">최애 한우인증점 Pick!</i></template>
			
			<template slot="content">
				
				<!-- top-area -->
				<tab-02-section-01-store-info :activeInfo="activeInfo" />
				<!-- swiper -->
				<div class="swiper">
					<client-only>
						<swiper ref="mySwiper"
							:options="swiperOption">
							<swiper-slide>
								<tab-02-section-01-store-item />
							</swiper-slide>
						</swiper>
					</client-only>
					<div class="swiper-button-prev" slot="button-prev"></div>
					<div class="swiper-button-next" slot="button-next"></div>
				</div>

				<div class="bottom-area">
					<p class="store-p">보고 계시는 한우 인증점이 마음에 든다면 좋은 이유를 댓글로 적고,<br><i class="point">♥ 좋아요 투표</i>버튼을 눌러주세요.</p>
					<div class="input-area">
						<vue-input 
							inputType="line-input"
							name=""
							id=""
							placeholder="좋은 이유를 입력해주세요! (30자 이내)"
							value="" 
						/>
						<bg-type-button 
							width="111px"
							height="60px"
							funcType="btn-vote"
							@click.native="step02ModalOn">
							투표
						</bg-type-button>
					</div>
				</div>

				<!-- board -->
				<tab-02-section-01-board-list
					:items="boardList" />
				<vue-pagenation :paginate="paginate"></vue-pagenation>
			</template>
        </vue-modal>

		<!-- step02 -->
		<vue-modal
			colorType="modal-pink"
			v-show="step02Modal"
			@close="close">
            <template slot="title">내 마음 속의 <i class="point">최애 한우인증점 Pick!</i></template>
			<template slot="sub-title">
				경품 발송 시 연락드릴 연락처를 입력해주세요.
				<i class="point">
					개인정보를 입력하시면 이벤트 참여가 완료됩니다.
				</i>
			</template>
			
			<template slot="content">
				<vue-tab></vue-tab>
				<vue-input 
				placeholder="이름"/>
				<vue-input 
				placeholder="전화번호"/>
				<vue-input 
				placeholder="이메일"/>
				<vue-agreement><i class="point">(필수)</i> 개인정보 활용 동의</vue-agreement>
				<vue-agreement>(선택) 마케팅 정보 수신 동의</vue-agreement>
				<div class="btn-area">
					<bg-type-button 
						funcType="btn-cancel"
						width="240px"
						@click.native="cancel">
						취 소
					</bg-type-button>
					<bg-type-button 
						funcType="btn-confirm"
						width="240px"
						@click.native="step03ModalOn">
						확 인
					</bg-type-button>
				</div>
			</template>
        </vue-modal>

		<!-- step03 -->
		<vue-modal
			colorType="modal-pink"
			v-show="step03Modal"
			@close="close">
            <template slot="title">내 마음 속의 <i class="point">최애 한우인증점 Pick!</i></template>
			<template slot="sub-title">
				이벤트 참여가 완료되었습니다.
				<i class="point">
					내일 다시 응모가 가능합니다.
				</i>
			</template>

			<template slot="content">
				<bg-type-button 
					funcType="btn-confirm"
					width="280px"
					class="confirm-btn"
					@click.native="confirm">
					확 인
				</bg-type-button>
			</template>
        </vue-modal>

	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class Tab02Section01 extends Vue {

	thumbList: Object[] = [
		{
			storeName: '늘푸름 홍천 한우',
			storeImg: require('@/assets/images/common/list_thumb.jpg')
		},
		{
			storeName: '세종한우',
			storeImg: require('@/assets/images/common/list_thumb2.jpg')
		},
		{
			storeName: '모심정',
			storeImg: require('@/assets/images/common/list_thumb.jpg')
		},
		{
			storeName: '다한우',
			storeImg: require('@/assets/images/common/list_thumb2.jpg')
		},
		{
			storeName: '끼리 한우',
			storeImg: require('@/assets/images/common/list_thumb.jpg')
		},
		{
			storeName: '고산미소 화성점',
			storeImg: require('@/assets/images/common/list_thumb2.jpg')
		},
		{
			storeName: '강화섬약쑥한우',
			storeImg: require('@/assets/images/common/list_thumb.jpg')
		}
	]
	
	activeInfo: object = {}


	boardList: Object[] = [
		{
			title: '리스트1',
			date: '2020.02.15'
		},
		{
			title: '리스트2',
			date: '2020.02.17'
		},
		{
			title: '리스트3',
			date: '2020.02.18'
		},
		{
			title: '리스트4',
			date: '2020.02.19'
		}
	]

	paginate: any[] = [
        {
			page: ''
        },
		{
			page: ''
        }
    ]

	step01Modal:     boolean = false
	step02Modal:     boolean = false
	step03Modal:     boolean = false

	swiperOption: any = {
		loop: true,
		slidesPerView: 1,
		spaceBetween: 30,
		pagination: {
		el: '.swiper-pagination',
		clickable: true,
		},
		navigation: {
		nextEl: '.swiper-button-next',
		prevEl: '.swiper-button-prev',
		},
	}
	
	modalOn(targetObj: object) {
		this.step01Modal = !this.step01Modal
		this.activeInfo = targetObj;		
	}

	close() {
        this.step01Modal = false
        this.step02Modal = false
    }

	step02ModalOn() {
		this.step01Modal = !this.step01Modal
		this.step02Modal = !this.step02Modal
	}
	
	step03ModalOn() {
		this.step02Modal = !this.step02Modal
		this.step03Modal = !this.step03Modal
	}

	cancel() {
		this.step02Modal = false
	}

	confirm() {
		this.step03Modal = false
	}
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.tab02-sec01 {
	background-color: #ffeaec;
	padding-bottom: 60px;
}

.wrap {
	width: 864px;
	display: flex;
	margin: 70px auto 0;
}

.tab {
	display: flex;
	justify-content: center;
	margin-top: 50px;
}

.thumb-list {
	justify-content: space-between;
	flex-wrap: wrap;
	margin-bottom: 30px;
}

.bg-type {
	display: flex;
	justify-content: center;
}

.modal-head {
	.point {
		color: #e15042;
	}
}

.modal-content {
	.bg-type {
		display: flex;
		justify-content: center;
	}
	.tab {
		margin-top: 0;
	}
	.btn-area {
		display: flex;
		justify-content: center;
		margin-top: 45px;
		.bg-type {
			margin: 0 10px;
		}
	}
}

.modal-subtit {
	.point {
		margin-top: 6px;
		margin-bottom: 30px;
		display: block;
		font-size: 18px;
		color: #ff5f50;
		line-height: 24px;
	}
}

.bottom-area {
	.store-p {
		margin: 17px 0;
		line-height: 24px;
		font-size: 18px;
		.point {
			color: #ff5f50;
			font-weight: 500;
		}
	}

	.input-area {
		display: flex;
		.bg-type {
			margin-left: 12px;
		}
	}
}

.swiper {
	position: relative;
}

.swiper-button-prev, .swiper-button-next {
	content: '';
	display: block;
	position: absolute;
	top: 0;
	bottom: 0;
	margin: auto;
	width: 19px;
	height: 31px;
	background: url('~@/assets/images/common/arrow.png') no-repeat;
	cursor: pointer;
}

.swiper-button-prev {
	left: -35px;
}

.swiper-button-next {
	right: -35px;
	transform: rotate(180deg);
}

</style>
