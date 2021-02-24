<template>
	<div class="board-list">
		<dl
			v-for="(item, key) of items"
			:key="key">
			<dt>{{ item.title }}</dt>
			<dd>{{ item.date }}</dd>
		</dl>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Prop} from "vue-property-decorator";
import Component from 'vue-class-component';

@Component
export default class Tab02Section01BoardList extends Vue {

	@Prop({default: []})  items!:	Object[]

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.board-list {
	margin-bottom: 20px;
	dl {
		display: flex;
		justify-content: space-between;
		padding: 10px 0;
		border-bottom: 1px solid #d4d4d4;
		dt {

		}
		dd {
			font-size: 14px;
			color: #9d9d9d;
			font-weight: 100;
			letter-spacing: 0;
		}
	}
}

</style>