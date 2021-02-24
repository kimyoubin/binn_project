<template>
	<div class="tab01-kv">
		<keyvisual-title>
			<template slot="title">한우먹고!<i class="point">한우 인증 GO ~!</i></template>
			<template slot="sub-title">한우 인증점 방문하여 한우를 먹고<br>
				<i class="point">한우 인증점 로고</i>가 나온 인증샷을 찍어 업로드 해주세요.<br>
				추첨을 통해 <i class="point">경품</i>을 드립니다.
			</template>
		</keyvisual-title>
		<keyvisual-content>
			<template slot="period">2018년 11월 16일 ~  12월 2일</template>
			<template slot="state">2018년 12월 6일</template>
			<template slot="gift">
				수험생 선물세트 8명 / 한우버거세트 기프티콘 11명<br>
				일반인 선물세트 6명 / 한우버거세트 기프티콘 11명
			</template>
		</keyvisual-content>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class Tab01Keyvisual extends Vue {

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.tab01-kv { background-color: #ffdb6f;}

</style>