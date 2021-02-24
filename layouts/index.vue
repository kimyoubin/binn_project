<template>
	<div>
		<nuxt /><!-- pages/index 가 들어옴 -->
		<page-footer />
	</div>
</template>

<script lang="ts">
import Vue from 'vue'
import PageFooter from "@/layouts/pageFooter.vue";
import {Component} from "vue-property-decorator";

@Component({
    components: {PageFooter}
})

export default class Index extends Vue {



}
</script>