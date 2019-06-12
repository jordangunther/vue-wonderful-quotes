<template>
    <div>
        <h1><strong>Quotes Added</strong></h1>
        <div class="quote-progress-bar">
            <span v-if="quoteCount == 0">{{ quoteCount }} / {{ maxQuotes }}</span>
            <div class="quote-progress" :style="{ width: (quoteCount / maxQuotes) * 100 + '%' }" v-else>
                {{ quoteCount }} / {{ maxQuotes }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quoteCount', 'maxQuotes'],
    }
</script>

<style scoped>
    .quote-progress-bar {
        height: 24px;
        background-color: lightgray;
        border-radius: 6px;
        overflow: hidden;
        text-align: center;
        color: white;

    }
    .quote-progress {
        background-color: dodgerblue;
        padding: 2px;
        text-align: center;
        color: white;
    }
</style>