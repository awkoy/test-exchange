<template lang="pug">
    header.header
        .container Hello World
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component
    export default class Header extends Vue {
        @Prop() private msg!: string;
    }
</script>

<style scoped lang="sass">
    .header
        position: absolute
        left: 0
        right: 0
        top: 0
        border-bottom: 1px solid #ccc
        font-size: 40px
        text-align: center
        padding: 10px 20px
</style>
