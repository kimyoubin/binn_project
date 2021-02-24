<template>
    <div>
		<!-- tab -->
        <main-tab
			:items="tabItems"
			:active="activeTab"
			@change="changeTab ">	
		</main-tab>
		
		<!-- tab content -->
        <tab-01-index v-if="activeTab === 0" />
        <tab-02-index v-if="activeTab === 1" />
    </div>
</template>

<script lang="ts">
import Vue from 'vue';
import {Component} from "vue-property-decorator"
import Tab01Index from "@/components/tab01/index.vue";
import Tab02Index from "@/components/tab02/index.vue";

// @ts-ignore
@Component({
    layout: 'index',
	components: {Tab01Index, Tab02Index}
})

export default class Index extends Vue {

	activeTab: number = 0

	tabItems: Object[] = [
		{
			tabEvent: 'Event1',
			tabIndex: '한우 먹고! 한우 인증 GO~!'
		},
		{
			tabEvent: 'Event2',
			tabIndex: '최애 한우인증점 Pick!'
		}
	]

	changeTab ( value: number ) {
		// alert('클릭');
		this.activeTab = value
	}

}
</script>


<style lang="scss" scoped>
@import "@/assets/scss/mixin"; 

</style>