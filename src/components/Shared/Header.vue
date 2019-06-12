<template>
    <div>
        <h1><strong>Quotes Added</strong></h1>
        <div class="quote-progress-bar">
            <span v-if="progress == 0"> 0 / 10</span>
            <div class="quote-progress" :style="{ width: progress + '0%' }" v-else>
                {{ progress }} / 10
            </div>
        </div>
    </div>
</template>

<script>
    import { quoteBus } from  '../../main';

    export default {
        data() {
            return {
                progress: 0
            }
        },
        created() {
            quoteBus.$on('quoteAdjusted', (quoteLength) => {
                this.progress = quoteLength;
            });
        }
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