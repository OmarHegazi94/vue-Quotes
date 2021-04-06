<template>
    <div>
        <div class="row text-start">
            <div class="col-sm-2"></div>
            <div class="col-sm-8">
                <form class="mb-3">
                    <div class="mb-3">
                        <label for="author" class="form-label">Quote Author</label>
                        <input type="text" class="form-control" id="author" placeholder="Enter the quote author" v-model="quoteAuthor">
                    </div>
                    <div class="mb-3">
                        <label for="quoteText" class="form-label">Quote</label>
                        <textarea class="form-control" id="quoteText" rows="3" v-model="quote"></textarea>
                    </div>
                </form>
            </div>
            <div class="col-sm-2"></div>
        </div>
        <div class="row">
            <div class="col-sm-2"></div>
            <div class="col-sm-8">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
            <div class="col-sm-2"></div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            quoteAuthor: '',
            quote: ''
        };
    },
    methods: {
        createNew() {
            if(this.quoteAuthor && this.quote){
                this.$emit('createNewQuote', {
                    author: this.quoteAuthor,
                    text: this.quote 
                })
    
                this.quoteAuthor = '',
                this.quote = ''
            }
        }
    }
};
</script>

<style></style>
