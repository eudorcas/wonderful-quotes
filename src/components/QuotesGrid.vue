<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteQuote(index)">
            <p>{{quote}}</p>
        </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';
    export default {
        props: ['quotes'],
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(id) {
                this.$emit('quoteWasDeleted', id);
            }
        }
    }
</script>

<style>
    
</style>