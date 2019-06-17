<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes" />
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
    import Header from './components/Header.vue';

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
            appHeader: Header,
        },
        methods: {
            insertQuote(quote) {
                if(this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete quotes first!');
                }
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
