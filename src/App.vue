<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-add-quote @quoteAdded="addQuote"></app-add-quote>
    <app-quote-list :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-list>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import Header from './components/Shared/Header.vue';
  import AddQuote from './components/Quotes/AddQuote.vue';
  import QuoteList from './components/Quotes/QuoteList.vue';
  import Footer from './components/Shared/Footer.vue';
  export default {
    data: function() {
      return {
        quotes: [],
        maxQuotes: 10
      }
    },
    methods: {
      addQuote(quote) {
        if (this.quotes.length >= this.maxQuotes) {
          return alert('please delete quotes first');
        }
        this.quotes.push(quote);
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1);
      }
    },
    components: {
      appHeader: Header,
      appAddQuote: AddQuote,
      appQuoteList: QuoteList,
      appFooter: Footer,
    }
  }
</script>

<style>
</style>
