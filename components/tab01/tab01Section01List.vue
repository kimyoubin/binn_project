<template>
	<div :class="listNum" class="list">
		<dl>
			<dt v-if="listNum==='list02'"><slot name="tit" /></dt>
			<dt v-else-if="listNum==='list03'"><slot name="tit" /></dt>
			<dd><slot name="sub-tit" /></dd>
		</dl>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from 'vue-class-component';

@Component
export default class Tab01Section01List extends Vue {

	@Prop({default: ''}) 		listNum?:		string;

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.list {
	display: flex;
	width: 640px;
	margin: 0 auto;
	padding-bottom: 40px;
	&.list02 {
		dl {
			height: 100px;
			align-items: stretch;
			flex-wrap: wrap;
			&::before {
				left: 40px;
				bottom: 10px;
				width: 150px;
				height: 78px;
				background: url('~@/assets/images/tab01/step02.png') center no-repeat;
			}
			dt {
				width: 100%;
			}
		}
	}
	&.list03 {
		dl {
			height: 100px;
			align-items: stretch;
			flex-wrap: wrap;
			&::before {
				left: 40px;
				bottom: 10px;
				width: 150px;
				height: 78px;
				background: url('~@/assets/images/tab01/step03.png') center no-repeat;
			}
			dt {
				width: 100%;
			}
		}		
	}
	&.list04 {
		dl {
			&::before {
				width: 102px;
				height: 100px;
				background: url('~@/assets/images/tab01/step04.png') center no-repeat;
			}
		}
	}
	dl {	
		position: relative;
		display: flex;
		align-items: center;
		width: 100%;
		height: 85px;
		padding-left: 215px;
		font-size: 18px;
		line-height: 20px;
		background: #fff;
		border-radius: 50px;
		box-shadow: 5px 5px 0 rgba(230,213,153,.2);			

		&::before {
			content: '';
			display: block;
			position: absolute;
			left: 65px;
			bottom: 0;
			width: 102px;
			height: 100px;
			background: url('~@/assets/images/tab01/step01.png') center no-repeat;
		}
		dt {
			display: flex;
			align-items: flex-end;
			width: 100%;
			margin-bottom: 5px;
			color: #e73c2b;
			font-weight: 700;
		}
		dd {
			width: 100%;
		}
	}
}

</style>