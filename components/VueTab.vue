<template>
	<div class="tab">

		<ul v-if="areaType" :class="areaType">
			<li class="on">전국</li>
			<li>수도권</li>
			<li>충청도</li>
			<li>전라도</li>
			<li>경상도</li>
			<li>강원도</li>
			<li>제주도</li>
		</ul>

		<ul class="age-type" v-else>
			<li class="on">10대</li>
			<li>20대</li>
			<li>30대</li>
			<li>40대</li>
			<li>50대 이상</li>
		</ul>
		
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from "vue-class-component";

@Component
export default class VueTab extends Vue {
	@Prop ({default : ''}) areaType?: 	string
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

.tab {
	ul {
		display: flex;
		li {
			display: inline-flex;
			justify-content: center;
			align-items: center;	
			cursor: pointer;
		}
	}
	.area-tab {
		width: 910px;
		height: 60px;
		border-radius: 30px;
		box-shadow: 5px 5px 0 rgba(0,0,0,.1);
		li {
			width: calc( 100%/7 );
			height: 60px;	
			font-size: 22px;	
			color: #342c2b;
			background-color: $white;			
			border-right: 1px solid #d3d3d3;
			&.on, &:hover {
				color: $white;
				font-weight: bold;
				border: none;
				background-color: #e4584b;
			}
			&:first-child {
				border-radius: 30px 0 0 30px;
			}			
			&:last-child {
				border-radius: 0 30px 30px 0;
				border: none;
			}
		}
	}
	.age-type {
		justify-content: space-between;
		width: 100%;
		margin-bottom: 20px;
		li {
			width: 100px;
			height: 60px;
			font-size: 20px;
			border: 1px solid #999;
			&.on, &:hover {
				font-weight: bold;
				color: #fff;
				border: 1px solid #3e3e3e;
				background-color: #3e3e3e;
			}
		}
	}
}

</style>