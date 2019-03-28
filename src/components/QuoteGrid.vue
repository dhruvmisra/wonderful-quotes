<template>
    <div class="container row">
        <app-quote class="d-inline-block animated zoomIn" 
                    v-for="(quote, index) in quotes"
                    :key="quote"
                    @click.native="deleteQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote';

    export default {
        props: {
            'quotes': Array
        },
        components: {
            'app-quote': Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style>
</style>
