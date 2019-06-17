<template>
    <div class="container">
        <app-quote-grid :quotes="quotes" />
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';

    export default {
        components: {
            appQuoteGrid: QuoteGrid,
        },
        data: () => ({
            maxQuotes: 10,
            quotes: [
                'Just a quote to see something',
            ],
        }),
    }
</script>

<style>
</style>
