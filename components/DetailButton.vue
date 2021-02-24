<template>
	<div class="detail-btn">
		<nuxt-link 
			:class="colorType"
			:style="{'width' : width}"
			to="">
			<p>자세히보기</p>
		</nuxt-link>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class DetailButton extends Vue {

	@Prop({default: 'light-gray'}) 	colorType?:		string;
	@Prop({default: '100px'}) 		width?:			string;

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

.detail-btn {
	&.on {
		a {
			p {
				&::after {
					top: 3px;
					border-left: 2px solid #666;
					border-top: 2px solid #666;
					border-bottom: 0;
					border-right: 0;
				}
			}	
		}
	}
	a {
		width: 100px;
		height: 24px;
		display: flex;
		justify-content: center;
		align-items: center;
		border: 1px solid $lightGray;
		border-radius: 15px;
		p {
			position: relative;
			display: inline-block;
			padding-right: 15px;
			font-size: 14px;
			color: #666;
			&::after {
				content: '';
				display: block;
				position: absolute;
				right: 0;
				bottom: 0;
				margin: auto;
				width: 8px;
				height: 8px;
				top: -3px;
				border-left: 0;
				border-top: 0;
				border-bottom: 2px solid #666;
				border-right: 2px solid #666;
				transform: rotate(45deg);
			}
		}
	}
}

</style>