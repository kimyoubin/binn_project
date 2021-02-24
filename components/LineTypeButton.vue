<template>
	<div class="line-type">
		<nuxt-link 
			:class="colorType"
			:style="{'width' : width}"
			to="">
			<p><slot/></p>
		</nuxt-link>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class LineTypeButton extends Vue {

	@Prop({default: 'line-type'}) 		btnType?:		string;
	@Prop({default: 'color-yellow'}) 	colorType?:		string;
	@Prop({default: '235px'}) 			width?:			string;

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.line-type {
	a {
		height: 30px;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 30px;
		p {
			position: relative;
			display: inline-block;
			padding-right: 10px;
			&::after {
				content: '';
				display: block;
				position: absolute;
				right: 0;
				top: 1px;
				bottom: 0;
				margin: auto;
				width: 8px;
				height: 8px;
				transform: rotate(45deg);
			}
		}
		&.color-yellow {
			border: 1px solid #fff;
			p {
				color: white;
				&::after {
					border-top: 2px solid $yellow;
					border-right: 2px solid $yellow;
				}
			}
		}
		&.color-pink {
			border: 1px solid #959090;
			p {
				color: #342c2b;
				&::after {
					border-top: 2px solid $pink;
					border-right: 2px solid $pink;
				}
			}
		}		
	}
}

</style>