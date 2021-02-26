<template>
	<ul>
		<li 
			v-for="(item, key) of items"
			:key="key"
			:class="listNum" 
			class="list"
			@click="$emit('click', item)"><!--3. 리스트를 클릭할때마다 tab02Section01에 있는 thumbList의 각각의 item을 호출(?)한다. tab02Section01에 있는 'click'이라는 함수?를 연결시켜줌-->
			<nuxt-link to="">
				<img :src="item.storeImg" alt="">
				<div class="info">
					<p>{{ item.storeName }}</p>
					<line-type-button colorType="color-pink">컨텐츠보고 투표 GO</line-type-button>
				</div>
			</nuxt-link>
		</li>
	</ul>
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
export default class Tab02Section01List extends Vue {

	@Prop({default: []}) 		items!:			Object[]
	@Prop({default: ''}) 		listNum?:		string

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

ul {
	display: flex;
	flex-wrap: wrap;
	.list {
		width: 270px;
		height: 310px;
		margin-bottom: 25px;
		margin-right: 25px;
		border-radius: 30px;
		background-color: #fff;
		box-shadow: 5px 5px 0 rgba(246,218,220);
		overflow: hidden;
		&:nth-child(3n) {
			margin-right: 0;
		}
		a {
			display: block;
			width: 100%;
			height: 100%;
		}
		.info {
			display: flex;
			flex-wrap: wrap;
			align-items: flex-end;
			height: 130px;
			padding: 20px 15px;
			p {
				align-self: stretch;
				width: 100%;
				font-size: 22px;
				margin-left: 10px;
				color: #3e2e2f;
				font-weight: bold;
			}
		}
	}

}

</style>