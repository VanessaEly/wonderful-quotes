<template>
    <div class="row">
        <form action="">
            <div class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
                <label>Quote</label>
                <textarea class="form-control" v-model="quote" name="Add Quote" id="add-quote" rows="3">
                </textarea>
            </div>
            <div class="form-group col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
                <!-- prevent modifier prevents submit to the server and page reload -->
                <button class="btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: () => ({
            quote: '',
        }),
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>

</style>
