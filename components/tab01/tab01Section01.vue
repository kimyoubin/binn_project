<template>
	<div class="tab01-sec01">

		<section-title>이벤트 참여 방법</section-title>

		<div class="way-list">
			<ul>
				<li>반드시 한우 유명한곳에 등록된 <b>한우 인증점에 방문</b>하셔야 합니다.</li>
				<li><span class="line">일반인이라면?</span> 한우 먹고 한우인증점 로고 &amp; 영수증 인증샷 업로드!</li>
				<li><span class="line">일반인이라면?</span> 한우 먹고 한우인증점 로고 &amp; 수험표 인증샷 업로드!</li>
			</ul>
		</div>

		<tab-01-section-01-list>
			<!-- <template slot="tit">ddd</template> -->
			<template slot="sub-tit">한우 유명한 곳에 등록된 <b>한우 인증점을 방문</b>해주세요.</template>
		</tab-01-section-01-list>
		<tab-01-section-01-list listNum="list02">
			<template slot="tit">일반 참여방법</template>
			<template slot="sub-tit">한우 유명한 곳에 등록된 <b>한우 인증점을 방문</b>해주세요.</template>
		</tab-01-section-01-list>
		<tab-01-section-01-list listNum="list03">
			<template slot="tit">수험생 참여방법</template>
			<template slot="sub-tit">한우 유명한 곳에 등록된 <b>한우 인증점을 방문</b>해주세요.</template>
		</tab-01-section-01-list>
		<tab-01-section-01-list listNum="list04">
			<template slot="tit">ddd</template>
			<template slot="sub-tit">한우 유명한 곳에 등록된 <b>한우 인증점을 방문</b>해주세요.</template>
		</tab-01-section-01-list>	
		
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class Tab01Section01 extends Vue {

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.tab01-sec01 {
	background-color: #fff3ca;
	padding-bottom: 30px;
}

.way-list {
	display: flex;
	justify-content: center;
	padding-bottom: 48px;
	ul {
		li {
			position: relative;
			line-height: 25px;
			font-size: 18px;
			color: #312928;
			&:nth-child(1) {
				padding-left: 20px;
			}
			&::before {
				content: 'v';
				display: block;
				position: absolute;
				left: 4px;
				right: 0;
				bottom: 0;
				margin: auto;
				font-family: 'BMJUA';
				font-size: 23px;
				color: #e95e53;
			}
			.line {
				display: inline-block;
				padding-left: 20px;
				font-weight: bold;
				box-shadow: inset 0 -10px 0 #fff; 
			}
		}
	}

}

</style>