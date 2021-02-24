<template>
	<div class="agreement">
		<div
			:class="{'on' : showAgreement}"
			class="checkbox-area">
			<vue-checkbox 
				name="check" 
				id="check" 
				for="check"><slot /></vue-checkbox>
			<detail-button 
				:class="{'on' : showAgreement}"
				@click.native="agreementOn" />
		</div>
		<transition name="slide-down">
			<div 
				v-if="showAgreement" 
				class="agreement-content">
				<div class="wrap">
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
					개인정보 활용동의입니다.<br>
				</div>
			</div>
		</transition>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from "vue-class-component";

@Component
export default class VueAgreement extends Vue {

	showAgreement:	boolean = false

	agreementOn() {
		this.showAgreement = !this.showAgreement
	}

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

.agreement {
	margin-bottom: 15px;
}

.checkbox-area {
	display: flex;
	align-items: center;
	&.on {
		margin-bottom: 15px;
	}
	.check-box {
		width: 235px;
	}
}

.agreement-content {
	width: 100%;
	height: 120px;
	background-color: #f3f3f3;
	overflow-y: scroll;
	.wrap {
		padding: 20px;
		line-height: 25px;
		text-align: left;
		color: #666;
	}
}

.slide-down-enter-active {	
    transition: all .5s ease;
}

.slide-down-enter, .slide-down-leave-to {
    height: 0;
    opacity: 0;
	transition: all .5s ease;
}

</style>