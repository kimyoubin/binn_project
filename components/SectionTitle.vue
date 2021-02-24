<template>
	<div class="sec-tit" :class="secType">
		<div class="sec-tit-wrap">
			<span></span>
			<p><slot/></p>
		</div>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class LineTypeButton extends Vue {

	@Prop({default: ''}) 		secType?:		string;

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.sec-tit {
	padding-top: 40px;
	padding-bottom: 30px;
	text-align: center;

	&.tab01-sec02 {
		.sec-tit-wrap {
			&::before, &::after {
				background: url('~@/assets/images/tab01/sec02_tit_ribbon.png') no-repeat;
			}
		}
		span {
			background: url('~@/assets/images/tab01/sec02_tit.png') center no-repeat;
		}
	}

	&.tab01-sec03 {
		padding-top: 80px;
		.sec-tit-wrap {
			&::before, &::after {
				width: 36px;
				height: 74px;
				background: url('~@/assets/images/tab01/sec03_tit_ribbon.png') no-repeat;
			}
		}
		span {
			display: none;
		}
		p {
			color: #fff;
		}
	}

	&.tab02-sec01 {
		.sec-tit-wrap {
			&::before, &::after {
				width: 39px;
				height: 37px;
				background: url('~@/assets/images/tab02/sec01_tit_ribbon.png') no-repeat;
			}
		}
		span {
			background: url('~@/assets/images/tab02/sec01_tit.png') center no-repeat;
		}
	}

	.sec-tit-wrap {
		position: relative;
		display: inline-block;
		&::before, &::after {
			content: '';
			display: block;
			position: absolute;
			bottom: 0;
			width: 44px;
			height: 90px;
			background: url('~@/assets/images/tab01/sec01_tit_ribbon.png') no-repeat;
		}
		&::before {
			left: -55px;
		}
		&::after {
			right: -55px;
			transform:rotate(0deg);
			transform: scaleX(-1);   
			filter: FlipH;
		}
	}
	span {
		display: block;
		width: 74px;
		height: 81px;
		margin: 0 auto;
		background: url('~@/assets/images/tab01/sec01_tit.png') center no-repeat;
	}
	p {
		display: block;
		font-family: 'BMJUA';
		font-size: 38px;
		color: #412a1d;
		text-align: center;
	}
}


</style>