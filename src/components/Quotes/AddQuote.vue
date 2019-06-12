<template>
    <div class="add-quote">
        <div class="add-quote__title">
            <h3>Quote</h3>
        </div>
        <textarea name="" id="" cols="30" rows="10" v-model="quote" placeholder="input quote"></textarea>
        <button @click="addQuote">Add Quote</button>
    </div>
</template>

<script>
    import { quoteBus } from  '../../main';

    export default {
        data() {
            return {
                quote: null,
            }
        },
        methods: {
            addQuote() {
                if (this.quote) {
                    if (this.quote.length > 0 && /\S/.test(this.quote)) {
                        quoteBus.$emit('addQuote', this.quote);
                    } else {
                        alert("no blank quotes allowed")
                    }
                } else {
                    alert('please insert a quote')
                }


            }
        }
    }
</script>

<style scoped>
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