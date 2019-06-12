<template>
    <div class="quote" @click="removeQuote()">
        {{ quote }}
    </div>
</template>

<script>
    import { quoteBus } from  '../../main';

    export default {
        props: ['quote'],
        methods: {
            removeQuote() {
                if (confirm("would you like to remove this quote?")) {
                    quoteBus.$emit('removeQuote', this.quote);
                }
            }
        }
    }
</script>

<style scoped>
    .quote {
        border: 1px solid darkgray;
        box-shadow: 1px 1px 2px darkgray;
        padding: 25px 20px;
        font-style: italic;
        font-size: 18px;
    }
</style>