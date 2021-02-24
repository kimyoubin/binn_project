<template>
	<div 
		class="input-box"
		:class="inputType">
		<input 
			type="text"
			:name="name"
			:id="id"
			:placeholder="placeholder"
			:value="value">
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class VueInput extends Vue {

	@Prop ({default: ''}) inputType?:		string
	@Prop ({default: ''}) name?:			string
	@Prop ({default: ''}) id?:				string
	@Prop ({default: ''}) placeholder?: 	string
	@Prop ({default: ''}) value?:			string

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

.input-box {
	width: 100%;
	height: 60px;
	margin-bottom: 22px;
	&.line-input {
		border: 1px solid #d3d3d3;
	}

	input {
		width: 100%;
		height: 100%;
		padding: 0 25px;
		font-size: 20px;
		background-color: #f3f3f3;
		&::placeholder {
			font-size: 20px;
			font-weight: 300;
			color: $lightGray;
		}
	}
}

</style>