<template>
	<div class="board">
		<tab-02-section-01-board-list />
		<vue-pagenation :paginate="paginate"></vue-pagenation>
	</div>
</template>

<script lang='ts'>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class Tab02Section01Board extends Vue {

	paginate: any[] = [
        {
            name: 'prev',
            href: '/'
        }
    ]

}
</script>

<style lang="scss" scoped>

@import "@/assets/scss/mixin";

.board {

}

</style>