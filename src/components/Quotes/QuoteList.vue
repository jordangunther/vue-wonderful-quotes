<template>
    <div class="quote-list">
        <app-quote v-for="quote in quotes" :quote="quote"></app-quote>
    </div>
</template>

<script>
    import { quoteBus } from  '../../main';

    import Quote from './Quote.vue'
    export default {
        data() {
            return {
                quotes: []
            }
        },
        components: {
            appQuote: Quote
        },
        created() {
            quoteBus.$on('addQuote', (quote) => {
                if (!this.quotes.includes(quote)) {
                    if (this.quotes.length < 10) {
                        this.quotes.push(quote);
                        quoteBus.$emit('quoteAdjusted', this.quotes.length);
                    } else {
                        alert("Exceeded your quote limit, to add a quote you must remove an existing quote.")
                    }
                } else {
                    alert("no duplicate quotes allowed")
                }

            });
            quoteBus.$on('removeQuote', (quote) => {
                for (var i=this.quotes.length-1; i>=0; i--) {
                    if (this.quotes[i] === quote) {
                        this.quotes.splice(i, 1);
                    }
                }
                quoteBus.$emit('quoteAdjusted', this.quotes.length);
            });
        }
    }
</script>

<style scoped>
    .quote-list {
        display: grid;
        grid-template-columns: 300px 300px 300px 300px;
        grid-column-gap: 30px;
        grid-row-gap: 15px;

        margin-bottom: 20px;
    }

</style>