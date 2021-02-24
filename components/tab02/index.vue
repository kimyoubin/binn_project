<template>
	<div>
		<tab-02-keyvisual />
		<tab-02-section-01 />
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import {Component} from "vue-property-decorator"
import Tab02Keyvisual from "@/components/tab02/tab02Keyvisual.vue";
import Tab02Section01 from "@/components/tab02/tab02Section01.vue";

// @ts-ignore
@Component({
	components: {Tab02Keyvisual, Tab02Section01}
})

export default class Index extends Vue {

}
</script>
