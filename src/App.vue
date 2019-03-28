<template>
    <div class="container">
        <h1 class="text-center mt-3">Wonderful Quotes</h1>
        <br><br>
        <app-header :length="quotes.length" :max="maxQuotes"></app-header>
        <br><br>
        <app-add @quoteAdded="addQuote"></app-add>
        <br>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <br>
        <div class="alert alert-info p-2 mt-1 text-center">Tip: Click on the box to delete it</div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid';
    import Header from './components/Header';
    import Add from './components/Add';

    export default {
        components: {
            'app-quote-grid': QuoteGrid,
            'app-header': Header,
            'app-add': Add
        },
        data() {
            return {
                maxQuotes: 10,
                quotes: [
                    'Just a quote to get you started'
                ]
            };
        },
        methods: {
            addQuote(quote) {
                if(this.quotes.length >= this.maxQuotes) {
                    alert('Max quotes limit reached. Delete some to continue.');
                    return;
                }
                this.quotes.push(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
h1 {
    font-family: 'Pacifico', cursive;
}
</style>
