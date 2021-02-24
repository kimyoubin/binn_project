<template>
    <div class="style-guide">
        <line-type-button>라인타입</line-type-button>
        <line-type-button colorType="color-pink">라인타입</line-type-button>

        <bg-type-button funcType="btn-cancel">취 소</bg-type-button>
        <bg-type-button funcType="btn-confirm">확 인</bg-type-button>
        <bg-type-button 
            width="360px"
            height="63px"
            funcType="btn-entry">응모하기</bg-type-button>
        <bg-type-button 
            width="360px"
            height="63px"
            funcType="btn-more">인증점 더보기</bg-type-button>
        <bg-type-button 
            width="111px"
            height="60px"
            funcType="btn-vote">투표</bg-type-button>
        <bg-type-button 
            fileType="btn-file" />

        <detail-button />

        <vue-checkbox 
            name="check" 
            id="check" 
            for="check"></vue-checkbox>

        <vue-input 
            name=""
            id=""
            placeholder="이름"
            value=""/>        
        <vue-input 
            inputType="line-input"
            name=""
            id=""
            placeholder="이름"
            value=""/>

        <bg-type-button 
            @click.native="yellowPopupOn" funcType="btn-confirm">Yellow Type Popup</bg-type-button>

        <bg-type-button 
            @click.native="pinkPopupOn" funcType="btn-confirm">Pink Type Popup</bg-type-button>
        
        <vue-modal
            v-show="yellowPopup"
            @close="close">
            <template slot="title">타이틀<i class="point">포인트</i>영역</template>
            <template slot="sub-title">서브타이틀영역</template>
        </vue-modal>
        <vue-modal
            v-show="PinkPopup"
            @close="close"
            colorType="modal-pink">
            <template slot="title">타이틀<i class="point">포인트</i>영역</template>
            <template slot="sub-title">서브타이틀영역</template>
        </vue-modal>
        <!-- <vue-modal colorType="modal-pink" padding="pd50">컨텐츠</vue-modal> -->

        <!-- <vue-pagenation :paginate="paginate"></vue-pagenation> -->
        <vue-pagenation :paginate="paginate"></vue-pagenation>

        <vue-tab></vue-tab>

    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Component from "vue-class-component";
import LineTypeButton from "~/components/LineTypeButton.vue";

@Component({
  components: {LineTypeButton}
})

export default class styleGuide extends Vue {

    yellowPopup:        boolean = false;
    PinkPopup:          boolean = false;

    yellowPopupOn() {
        this.yellowPopup = !this.yellowPopup 
    }
    
    pinkPopupOn() {
        this.PinkPopup = !this.PinkPopup 
    }

    close() {
        this.yellowPopup = false
        this.PinkPopup = false
    }

}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/mixin";

.style-guide { height: 100vh; background: #ffd8d8;}

</style>
