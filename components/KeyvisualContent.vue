<template>
	<div class="kv-content" :class="kvType">
		<ul>
			<li>
				<dl>
					<dt>이벤트 기간 :</dt>
					<dd><slot name="period"/></dd>
				</dl>
			</li>
			<li>
				<dl>
					<dt>당첨자 발표 :</dt>
					<dd><slot name="state"/></dd>
				</dl>
			</li>
			<li>
				<dl>
					<dt>이벤트 경품 :</dt>
					<dd><slot name="gift"/></dd>
				</dl>
			</li>
		</ul>
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

.kv-content {
	position: relative;
	height: 670px;
	background: url('~@/assets/images/tab01/kv_con.png') center no-repeat;
	ul {
		position: absolute;
		bottom: 88px;
		left: 267px;
		li {
			dl {
				display: inline-flex;
				align-items: flex-start;
				line-height: 32px;
			}
			dt {
				font-size: 20px;
				color: #e57507;
				font-weight: 500;
			}
			dd {
				font-size: 18px;
				margin-left: 25px;
			}
		}
	}
	&.tab02-type {
		height: 600px;
		background: url('~@/assets/images/tab02/kv_con.png') center no-repeat;
		ul {
			bottom: 91px;
			li {
				dt {
					color: #ff5f50;
				}
			}
		}
	}
}


</style>