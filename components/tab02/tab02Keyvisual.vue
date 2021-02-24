<template>
	<div class="tab02-kv">
		<keyvisual-title kvType="tab02-type">
			<template slot="title">내 마음속의 최애<i class="point">한우 인증점 Pick!</i></template>
			<template slot="sub-title">한우 인증점 컨텐츠를 확인하고<br>
				마음에 드는 <i class="point">최애 한우인증점</i>에 좋아요 댓글을 남겨주세요.<br>
				추첨을 통해 <i class="point">경품</i>을 드립니다.
			</template>
		</keyvisual-title>

		<keyvisual-content kvType="tab02-type">
			<template slot="period">2018년 11월 26일 ~  12월 9일</template>
			<template slot="state">2018년 12월 13일</template>
			<template slot="gift">한우선물세트 10명, 한우 불고기 버거 세트 30명</template>
		</keyvisual-content>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class Tab02Keyvisual extends Vue {

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.tab02-kv {background: linear-gradient(180deg, #ffdfdf 20%, #ffcdcd 60%);}

</style>