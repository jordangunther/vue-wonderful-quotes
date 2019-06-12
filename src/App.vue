<template>
  <div class="container">
    <app-header></app-header>
    <app-add-quote></app-add-quote>
    <app-quote-list></app-quote-list>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import Header from './components/Shared/Header.vue';
  import AddQuote from './components/Quotes/AddQuote.vue';
  import QuoteList from './components/Quotes/QuoteList.vue';
  import Footer from './components/Shared/Footer.vue';
  export default {
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
