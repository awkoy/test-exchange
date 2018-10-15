<template lang="pug">
    footer.footer
        .copyright Hello World
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component
    export default class Footer extends Vue {
        @Prop() private msg!: string;
    }
</script>

<style scoped lang="sass">
    .footer
        background: #ccc
        height: 70px
        display: flex
        justify-content: center
        align-items: center
</style>
