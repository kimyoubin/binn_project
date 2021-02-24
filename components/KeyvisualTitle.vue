<template>
	<div class="kv-tit" :class="kvType">
		<h1><slot name="title" /></h1>
		<p><slot name="sub-title" /></p>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class LineTypeButton extends Vue {

	@Prop({default: ''}) 		kvType?:		string;

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.kv-tit {
	padding-top: 70px;
	h1 {
		position: relative;
		text-align: center;
		font-family: 'BMJUA';
		font-size: 72px;
		margin-bottom: 30px;
		.point {
			display: block;
			font-size: 75px;
			color: #c83030;
		}
		&::before, &::after {
			content: '';
			display: block;
			position: absolute;
			top: -10px;
			width: 89px;
			height: 180px;
			background: url('~@/assets/images/tab01/kv_tit_ribbon.png') no-repeat;
		}
		&::before {
			left: 185px;
		}
		&::after {
			right: 185px;
			transform:rotate(0deg);
			transform: scaleX(-1);   
			filter: FlipH;
		}
	}

	p {
		text-align: center;
		font-size: 20px;
		line-height: 26px;
		color: #2d2929;
		.point {
			color: #e02727;
			font-weight: 500;
		}
	}

	&.tab02-type {
		h1 {
			.point { 
				color: #e15042;
			}
			&::before, &::after {
				width: 159px;
				height: 253px;
				background: url('~@/assets/images/tab02/kv_tit_ribbon.png') no-repeat;
			}
			&::before {
				left: 30px;
			}
			&::after {
				right: 30px;
			}
		}
		p {
			.point {
				color: #e15042;
			}
		}
	}
}


</style>