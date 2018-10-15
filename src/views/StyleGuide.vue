<template lang="pug">
    main.style-guide
        .container
            h1 Style Guide Project
            .style-guide__block
                h2 Titles
                .style-guide__content
                    h1 H1 Lorem ipsum dolor sit amet
                    h2 H2 Lorem ipsum dolor sit amet
                    h3 H3 Lorem ipsum dolor sit amet
                    h4 H4 Lorem ipsum dolor sit amet
                    h5 H5 Lorem ipsum dolor sit amet
            .style-guide__block
                h2 Buttons
                .style-guide__content
                    p
                        Button default
                        Button(disable) disabled
                        Button(large="true") large
                    p
                        Button(mod="small") small
                        Button(mod="small" disable) small
                        Button(mod="small" large="true") small
                    p
                        Button(border="true") border
                        Button(border="true" disable) border
                        Button(border="true" large="true") border
                    p
                        Button(mod="small" border="true") border
                        Button(mod="small" border="true" disable) border
                        Button(mod="small" border="true" large="true") border
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import Button from '@/components/ui/Button.vue';

    @Component({
        components: {
            Button,
        },
    })
    export default class StyleGuide extends Vue {}
</script>

<style scoped lang="sass">
    .style-guide
        position: relative
        &__content
            padding-left: 40px
            border-left: 1px solid #ccc
    .btn
        margin-right: 20px
        margin-bottom: 40px
</style>