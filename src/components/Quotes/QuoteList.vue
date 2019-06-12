<template>
    <div class="quote-list">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
    import { quoteBus } from  '../../main';
    import Quote from './Quote.vue'

    export default {
        props: ['quotes'],

        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
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