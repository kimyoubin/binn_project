<template>
	<div :class="listNum" class="list">
		<dl>
			<dt></dt>
			<dd><slot /></dd>
		</dl>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from 'vue-class-component';

@Component
export default class Tab02Section01List extends Vue {

	@Prop({default: ''}) 		listNum?:		string;

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.list {
	position: relative;
	width: 270px;
	height: 240px;
	margin: 12px;
	background: #ffd6da;
	border-radius: 50px;
	border: 4px solid #fff;

	&.list02 {
		dl {
			dt {
				background: url('~@/assets/images/tab02/step02.png') no-repeat;
			}
		}
	}

	&.list03 {
		dl {
			dt {
				background: url('~@/assets/images/tab02/step03.png') no-repeat;
			}
		}
	}
	
	dl {
		dt {
			position: absolute;
			top: -84px;
			left: 0;
			right: 0;
			margin: auto;
			width: 161px;
			height: 162px;
			background: url('~@/assets/images/tab02/step01.png') no-repeat;
		}
		dd {
			margin-top: 95px;
			text-align: center;
			font-size: 20px;
			line-height: 26px;
		}
	}
}

</style>