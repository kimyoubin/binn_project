<template>
	<div class="tab01-sec02">
		<section-title secType="tab01-sec02">내가 받을 행운의 경품은?</section-title>
		<div class="sec02-con">
			<ul>
				<li>
					<dl>
						<dt>수험생 선물세트</dt>
						<dd><i class="point">&#42;</i> 한우선물세트 (30만원 상당) / 1명</dd>
						<dd><i class="point">&#42;</i> 한우선물세트 (10만원 상당) / 2명</dd>
						<dd><i class="point">&#42;</i> 한우선물세트 (5만원 상당) / 5명</dd>
						<dd><i class="point">&#42;</i> 한우버거세트 기프티콘 / 11명</dd>
					</dl>
				</li>
				<li>
					<dl>
						<dt>일반인 선물세트</dt>
						<dd><i class="point">&#42;</i> 한우선물세트 (20만원 상당) / 1명</dd>
						<dd><i class="point">&#42;</i> 한우선물세트 (5만원 상당) / 5명</dd>
						<dd><i class="point">&#42;</i> 한우버거세트 기프티콘 / 11명</dd>
					</dl>
				</li>
			</ul>
		</div>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class Tab01Section02 extends Vue {

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.tab01-sec02 {
	padding-bottom: 60px;
	background-color: #ffdb6f;
}

.sec02-con {
	position: relative;
	display: flex;
	justify-content: center;
	height: 602px;
	background: url('~@/assets/images/tab01/sec02_con.png') center no-repeat;
	ul {
		position: absolute;
		left: 185px;
		bottom: 30px;
		display: flex;
		justify-content: center;
		li {
			margin: 0 30px;
			dl {}
			dt { 
				text-align: center;
				margin-bottom: 8px;
				font-size: 20px;
				color: #e57507;
			}
			dd {
				line-height: 28px;
				font-size: 18px;
				.point {
					color: #e57507;
				}
			}
		}
	}
}

</style>