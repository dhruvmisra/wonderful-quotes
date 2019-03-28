<template>
    <div class="container text-center">
        <h4>Add a quote</h4>
        <textarea class="form-control col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 mx-auto" 
                    id="add" 
                    cols="30" 
                    rows="4" 
                    v-model="quote"></textarea>
        <br>
        <button class="btn btn-primary" 
                @click="addQuote()" 
                :class="[{'btn-secondary': !quote.length}, {disabled: !quote.length}]"
                >Add Quote</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                quote: ''
            };
        },
        methods: {
            addQuote() {
                if(this.quote.length)
                    this.$emit('quoteAdded', this.quote);
            }
        }
    }
</script>

<style>
</style>
