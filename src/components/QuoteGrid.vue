<template>
    <div class="row">
        <app-quote v-for="(quote, key) in quotes" :key="key">
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
}
</script>

<style>

</style>
