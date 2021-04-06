<template>
    <div class="row">
        <app-quote v-for="(quote, index) in Quotes" :key="index" @click="$emit('deleteQuote', index)">
            
            <blockquote class="blockquote mb-0">
                <p>{{ quote.text }}</p>
                <footer class="blockquote-footer">{{ quote.author }}</footer>
            </blockquote>

        </app-quote>
    </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
    props: ["Quotes"],
    components: {
        appQuote: Quote,
    },
};
</script>

<style></style>
