<template lang="pug">
  router-link(v-if="href" :to="href" :class="[`btn ${getModify}`, {'large': large}, {'full': full}, {'border': border }]" :disabled="disable")
    slot
  button.btn(v-else @click="action()" :class="[`btn ${getModify}`, {'large': large}, {'full': full }, {'border': border }]" :disabled="disable")
    slot
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component
    export default class Button extends Vue {
        @Prop() private href!: string;
        @Prop() private action!: () => void;
        @Prop() private mod!: string;
        @Prop() private full!: boolean;
        @Prop() private disable!: boolean;
        @Prop({default: false}) private large!: boolean;
        @Prop() private border!: boolean;

         get getModify() {
            const { mod } = this;
            return mod ? `btn__${mod}` : 'btn__default';
         }
    }
</script>

<style lang="sass" scoped>
    @import '@/assets/styles/_variables.sass'

    .btn
        height: 46px
        padding-left: 20px
        padding-right: 20px
        display: inline-flex
        align-items: center
        position: relative
        justify-content: center
        box-sizing: border-box
        font-size: 16px
        border-radius: 5px
        cursor: pointer
        letter-spacing: 0.3px
        background-color: $blue
        text-align: center
        color: $white
        font-family: $f-bold
        transition: .3s

        &__default
            box-shadow: 2px 3px 16px rgba(87, 94, 232, 0.53)
            &:hover
                box-shadow: none
                background-color: #475ff2
            &:active
                box-shadow: inset 0 1px 1px #0c1d7f
                background-color: #3048dd

        &.large
            width: 239px

        &.full
            width: 100%

        &:disabled,&[disabled]
            background-color: #e6e7ff
            color: #bfc1f1
            box-shadow: none
            cursor: default
            &:hover
                background-color: #e6e7ff
                color: #bfc1f1

        &__small
            height: 32px
            border-radius: 100px
            font-size: 14px
            line-height: 32px
            &:hover
                box-shadow: none
                background-color: #475ff2
            &:active
                box-shadow: inset 0 1px 1px #0c1d7f
                background-color: #3048dd

        &.border
            color: $blue
            background-color: $white
            border: 1px solid $blue
            box-shadow: none
            &:hover
                border: 1px solid #475ff2
                background-color: #475ff2
                color: $white
            &:active
                box-shadow: inset 0 1px 1px #0c1d7f
                background-color: #3048dd
            &:disabled,&[disabled]
                color: #bfc1f1
                background-color: $white
                box-shadow: none
                border: 1px solid #bfc1f1
                cursor: default
</style>