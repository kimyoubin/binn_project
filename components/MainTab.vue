<template>
	<ul>
		<li
			v-for="(item, key) of items" 
			:key="key"
			:class="{ 'on' : active === key }"
			@click="$emit('change', key)">
			<i class="point">{{ item.tabEvent }}</i>
			{{ item.tabIndex }}
		</li>		
	</ul>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class MainTab extends Vue {

	@Prop({default: []}) 	items!:			Object[]
	@Prop () 			   active?: 		number

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

ul {
	display: flex;
	justify-content: center;
	align-items: center;
	width: 100%;
	height: 60px;
	li {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 50%;
		height: 100%;
		font-family: 'BMJUA';
		font-size: 28px;
		color: #fff;
		border-radius: 20px 20px 0 0;
		background-color: #b3b3b3;
		cursor: pointer;
		&.on {
			color: #000;
			&:nth-child(1) {
				background-color: #ffdb6f;
				.point {
					color: #c83030;
				}
			}
			&:nth-child(2) {
				background-color: #f48585;
				.point {
					color: #feff9e;
				}
			}
		}
		.point { 
			display: inline-block;
			margin-right: 5px;
		}
		
	}
}

</style>