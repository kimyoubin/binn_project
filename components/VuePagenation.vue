<template>
	<div class="pagenation">
		<div class="wrap">
			<a href="#none" class="arrow first"></a>
			<a href="#none" class="arrow pre"></a>

			<!-- <a href="#none" class="on">1</a>
			<a href="#none">2</a>
			<a href="#none">3</a>
			<a href="#none">4</a>
			<a href="#none">5</a> -->

			<a 
				v-for="(item, key) of paginate"
				:key="key">{{ key + 1 }}</a>

			<a href="#none" class="arrow next"></a>
			<a href="#none" class="arrow last"></a>
		</div>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class VuePagenation extends Vue {

	@Prop({default:[]})		paginate!:	Object[]

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

.pagenation {
	display: flex;
	justify-content: center;
	align-items: center;
	.wrap {	
		display: inline-flex;
		justify-content: center;
		align-items: center;
	}
	a {
		display: inline-block;
		margin: 0 8px;
		color: #4d4d4d;
		font-size: 15px;
		font-weight: 300;
		cursor: pointer;
		&.on {
			color: #ff887d;
			font-weight: 700;
		}
	}
	.arrow {
		width: 24px;
		height: 24px;
		&.first {
			margin-right: 5px;
			background: url('~@/assets/images/common/page_arrow2.png') no-repeat;
		}
		&.pre {
			background: url('~@/assets/images/common/page_arrow.png') no-repeat;
		}
		&.next {
			background: url('~@/assets/images/common/page_arrow.png') no-repeat;
			transform: rotate(180deg);
		}
		&.last {
			margin-left: 5px;
			transform: rotate(180deg);
			background: url('~@/assets/images/common/page_arrow2.png') no-repeat;
		}
	}
}

</style>