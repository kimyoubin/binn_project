<template>
	<div class="check-box">
		<input
			type="checkbox"
			:name="name"
			:id="id">
        <label :for="id"><slot/></label>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class VueCheckbox extends Vue {

	@Prop ({default: ''}) name?: 	string
	@Prop ({default: ''}) id?: 		string

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

.check-box {
	.point {
		color: #c83030;
	}
	input {
		display: none;

		&:checked {
			+label {
				&:after {
					background-color: $red;
				}
			}
		}

		+label {
            position: relative;
			display: block;
			padding-left: 35px;
			color: #333;
			text-align: left;
			&:before,
			&:after {
				content: '';
				display: inline-block;
				position: absolute;
				margin: auto;
			}
			&:before {
				left: 2px;
				top: 0;
				width: 19px;
				height: 15px;
				background: url('~@/assets/images/common/checkbox.png') no-repeat;
				z-index: 1;
			}

			&:after {
				top: 0;
				bottom: 0;
				left: 0;
				width: 24px;
				height: 24px;
				background-color: #e6e6e6;
			}
		}
	}
}


</style>