<template>
	<div>
		<tab-01-keyvisual />
		<tab-01-section-01 />
		<tab-01-section-02 />
		<tab-01-section-03 />
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Component} from "vue-property-decorator"
import Tab01Keyvisual from "@/components/tab01/tab01Keyvisual.vue";
import Tab01Section01 from "@/components/tab01/tab01Section01.vue";
import Tab01Section02 from "@/components/tab01/tab01Section02.vue";


// @ts-ignore
@Component({
	components: { Tab01Keyvisual, Tab01Section01, Tab01Section02}
})

export default class Index extends Vue {

}
</script>
