<template>
	<div class="tab01-sec03">
		<section-title secType="tab01-sec03">이벤트 응모하기</section-title>
		<div class="wrap">
			<p class="sub-tit">한우 유명한 곳에 등록된 인증점 방문 후 한우를 먹고<br>
				한우 인증점 로고가 나온 인증샷을 찍어 업로드하면 한우 선물이 한 번 더!
				<i class="point">* 일반인과 수험생 참여방법이 상이하오니 이벤트 참여방법을 확인하세요!</i>
			</p>
		</div>	
		<bg-type-button 
			width="360px"
			height="63px"
			funcType="btn-entry"
			@click.native="modalOn">응모하기</bg-type-button>	
		
		<!-- step01 -->
		<vue-modal
			v-show="step01Modal"
			@close="close">
            <template slot="title">한우 먹고! <i class="point">한우 인증 GO ~!</i></template>
            <template slot="sub-title">수험생과 일반 참여 방법이 다릅니다!<br>참여 유형을 선택해주세요.</template>

			<template slot="content">
				<ul class="select">
					<li @click="examineeTypeOn">수험생으로 참여할꺼에요!</li>
					<li @click="publicTypeOn">일반으로 참여할꺼에요!</li>
				</ul>
			</template>
        </vue-modal>

		<!-- step02 -->
		<vue-modal
			v-show="step02Modal"
			@close="close">
            <template slot="title">한우 먹고! <i class="point">한우 인증 GO ~!</i></template>
            <template  slot="sub-title">
				경품 발송 시 연락드릴 연락처를 입력해주세요.
				<i class="point">한우 인증점 로고와 
					<span v-if="examineeType">수험표가</span>
					<span v-else>영수증이</span>
					나온 이미지를 업로드 후,<br>
					개인정보를 남겨주셔야 이벤트 참여가 완료됩니다.
				</i>
			</template>

			<template slot="content">
				<div class="input-area">
					<div class="flex-box">
						<vue-input 
							placeholder="이미지는 한장만 업로드 가능합니다."/>
						<bg-type-button 
            				fileType="btn-file" />
					</div>
					<span class="info">&#42; Jpg, Jpeg, Png 파일만 업로드 가능합니다.</span>
				</div>				
				<vue-input 
					placeholder="이름"/>
				<vue-input 
					placeholder="전화번호"/>
				<vue-input 
					placeholder="이메일"/>

				<vue-agreement><i class="point">(필수)</i> 개인정보 활용 동의</vue-agreement>
				<vue-agreement>(선택) 마케팅 정보 수신 동의</vue-agreement>

				<bg-type-button 
					funcType="btn-confirm"
					width="280px"
					class="confirm-btn"
					@click.native="step03ModalOn">
					확 인
				</bg-type-button>
			</template>
        </vue-modal>

		<!-- step03 -->
		<vue-modal
			v-show="step03Modal"
			@close="close">
            <template slot="title">한우 먹고! <i class="point">한우 인증 GO ~!</i></template>
			<template slot="sub-title">이벤트 참여가 완료되었습니다.</template>

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
import {Prop} from "vue-property-decorator";
import Component from 'vue-class-component';

@Component
export default class Tab01Section03 extends Vue {

	step01Modal:     boolean = false;
	step02Modal:     boolean = false;
	step03Modal:     boolean = false;

	examineeType:    boolean = false;
	publicType:      boolean = false;

	modalOn() {
		this.step01Modal = !this.step01Modal
	}

	close() {
        this.step01Modal = false
        this.step02Modal = false
        this.step03Modal = false

        this.examineeType = false
        this.publicType = false
    }

	// 수험생
	examineeTypeOn() {
		alert('수험생입니다.');
		this.step01Modal = !this.step01Modal
		this.step02Modal = !this.step02Modal

		this.examineeType = !this.examineeType
	}

	// 일반인
	publicTypeOn() {
		alert('일반입니다.');
		this.step01Modal = !this.step01Modal
		this.step02Modal = !this.step02Modal

		this.publicType = !this.publicType
	}

	step03ModalOn() {
		this.step02Modal = !this.step02Modal
		this.step03Modal = !this.step03Modal
	}

	confirm() {
		this.step03Modal = false

        this.examineeType = false
        this.publicType = false
	}

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.tab01-sec03 {
	padding-bottom: 50px;
	background-color: #654d40;
	text-align: center;
	.wrap {
		display: flex;
		justify-content: center;
	}
	.sub-tit {
		font-size: 20px;
		color: #fff;
		line-height: 26px;
		.point {
			display: block;
			margin-top: 15px;
			margin-bottom: 25px;
			color: #ffec6f;
			padding: 1px 10px;
			background-color: #2c2624;
		}
	}
	.bg-type {
		display: flex;
		justify-content: center;
	}
}

.modal-head {
	.point {
		color: #c83030;
	}
}

.modal-subtit {
	.point {
		margin-top: 6px;
		margin-bottom: 30px;
		display: block;
		font-size: 18px;
		color: #c86930;
		line-height: 24px;
	}
}

.select {
	display: flex;
	justify-content: space-between;
	align-items: flex-end;
	margin-top: 30px;
	li {
		overflow: hidden;
		cursor: pointer;
		text-indent: -9999px;
		&:hover {
			&:nth-child(1) {
				background-position: 0 0;		
			}
			&:nth-child(2) {
				background-position: 0 0;		
			}
		}
		&:nth-child(1) {
			width: 280px;
			height: 365px;
			background: url('~@/assets/images/tab01/popup_select01.png') no-repeat;	
			background-position: -280px 0;			
		}
		&:nth-child(2) {
			width: 264px;
			height: 340px;
			background: url('~@/assets/images/tab01/popup_select02.png') no-repeat;	
			background-position: -264px 0;	
		}
	}
}


.flex-box {
	display: flex;
	align-items: center;
}

.input-area {
	margin-bottom: 12px;
	.flex-box {
		.bg-type {
			margin-left: 8px;
		}
		.input-box {
			margin-bottom: 0;
		}
	}
	.info {
		display: block;
		margin-top: 8px;
		margin-left: 20px;
		text-align: left;
		color: #999;
		font-weight: 300;
	}
}

.confirm-btn {
	margin-top: 30px;
}

</style>