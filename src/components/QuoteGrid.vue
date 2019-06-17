<template>
    <div class="row">
        <!-- Native modifier - react to clicks on the native element of the component,
        which means that this click will be added to the first div of the quote component -->
        <app-quote 
            v-for="(quote, index) in quotes"
            :key="index"
            @click.native="deleteQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        components: {
            appQuote: Quote,
        },
        props: ['quotes'],
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            },
        }
    }
</script>

<style>

</style>
