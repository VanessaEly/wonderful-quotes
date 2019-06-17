<template>
    <div class="container">
        <app-new-quote @quoteAdded="insertQuote" />
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"/>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: click on a quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: () => ({
            maxQuotes: 10,
            quotes: [
                'Just a quote to see something',
            ],
        }),
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
        },
        methods: {
            insertQuote(quote) {
                this.quotes.push(quote);
            },
            deleteQuote(index) {
                // removing only the current index from the quotes list
                this.quotes.splice(index, 1);
            },
        }
    }
</script>

<style>
</style>
