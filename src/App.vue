<template lang="pug">
  #app
    Header
    router-view
    Footer
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import Header from '@/components/parts/Header.vue';
    import Footer from '@/components/parts/Footer.vue';

    @Component({
        components: {
            Header,
            Footer,
        },
    })
    export default class Home extends Vue {}
</script>
