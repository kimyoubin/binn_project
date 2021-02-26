<template>
	<div class="store-list">
		<div class="top-area">
			<p>{{ activeInfo.storeName }}</p><!--2. activeInfo라는 객체를 여기에서 받아서 dom에 뿌려준다.-->
			<div class="btn-area">
				<line-type-button 
					colorType="color-pink"
					width="100px"
					>홈페이지</line-type-button>
				<line-type-button 
					colorType="color-pink"
					width="120px"
					>후기 포스팅</line-type-button>
			</div>
		</div>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import LineTypeButton from "@/components/LineTypeButton.vue";
import Component from 'vue-class-component';

// @ts-ignore
@Component({
	components: {LineTypeButton}
})

export default class Tab02Section01StoreInfo extends Vue {
	
	// activeInfo 빈 객체를 Prop으로 만들어준다.
	@Prop() activeInfo!: Object[]

	// @Prop({default: []})		item!:				Object[]
	// @Prop({default: ''})		storeInfoName?:		string

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.store-list {
	.top-area {
		display: flex;
		justify-content: space-between;
		margin-bottom: 15px;
		p {
			font-size: 28px;
			font-weight: bold;
		}
		.btn-area{
			display: flex;
			.line-type {
				margin-left: 13px;
			}
		}
	}	
}

</style>