<template>
    <div class="add-quote">
        <div class="add-quote__title">
            <label>Quote</label>
        </div>
        <textarea name="" id="" cols="30" rows="10" v-model="quote" placeholder="input quote"></textarea>
        <button @click.prevent="addQuote">Add Quote</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                quote: '',
            };
        },
        methods: {
            addQuote() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style scoped>
    label {
        font-size: 20px;
        margin: 10px 0;
    }
    .add-quote {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .add-quote__title, textarea {
        width: 600px;
        max-width: 100%;
    }
    textarea {
        margin-bottom: 20px;
    }
    button {
        background-color: dodgerblue;
        color: white;
        padding: 8px 12px;
        font-weight: bold;
        border: none;
        border-radius: 6px;
        margin-bottom: 20px;
    }

</style>