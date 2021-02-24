<template>
	<div class="bg-type">

		<div 
			v-if="fileType" 
			:class="fileType"
			class="btn-file">
			<label for="input-file"></label>
			<input type="file" id="input-file">
		</div>
		

		<nuxt-link 
			v-else
			:class="funcType"
			:style="{
				'width' : width,
				'height' : height,
			}"
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
export default class BgTypeButton extends Vue {

	@Prop({default: 'bg-type'}) 				btnType?:		string;
	@Prop({default: ''}) 						funcType?:		string;
	@Prop({default: ''}) 						fileType?:		string;
	@Prop({default: '240px'}) 					width?:			string;
	@Prop({default: '54px'}) 					height?:		string;

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.bg-type {
	a {
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 30px;
		p {
			font-size: 24px;
			color: $white;
		}
		&.btn-cancel {
			background-color: $lightGray;
		}
		&.btn-confirm {
			background-color: $darkGray;
		}
		&.btn-entry {
			font-family: 'BMJUA';
			box-shadow: 5px 5px 1px rgba(0,0,0,.1);
			background-color: #fffa6f;
			p {
				position: relative;
				padding-right: 25px;
				font-size: 34px;
				color: #483d37;
				&::after {
					content: '';
					display: block;
					position: absolute;
					right: 0;
					top: -3px;
					bottom: 0;
					margin: auto;
					width: 16px;
					height: 26px;
					background: url('~@/assets/images/tab01/btn_entry_arrow.png');
				}
			}
		}
		&.btn-more {
			box-shadow: 5px 5px 1px rgba(0,0,0,.1);
			background-color: $white;
			p {
				position: relative;
				padding-left: 34px;
				font-size: 22px;
				font-weight: 700;
				color: #3e2e2f;
				&::before {
					content: '';
					display: block;
					position: absolute;
					left: 0;
					top: 0;
					bottom: 0;
					margin: auto;
					width: 23px;
					height: 23px;
					background: url('~@/assets/images/common/ico_add.png');
				}
			}
		}
		&.btn-vote {
			border-radius: 5px;
			background-color: #ff887d;
			p {
				position: relative;
				font-size: 20px;
				padding-left: 33px;
				&::before {
					content: '';
					display: block;
					position: absolute;
					left: 0;
					top: 0;
					bottom: 0;
					margin: auto;
					width: 27px;
					height: 26px;
					background: url('~@/assets/images/common/ico_heart.png');
				}
			}
		}
	}
	.btn-file {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 60px;
		height: 60px;
		border-radius: 5px;
		background-color: #bababa;
		label {
			width: 39px;
			height: 39px;
			background: url('~@/assets/images/common/ico_file.png') center no-repeat;
		}
		input {
			display: none;
		}
	}
}

</style>