<template>
  <div class="container">
    <appHeader :QuoteCount="quotes.length" :MaxCount="maxQuotes"></appHeader>
    <appNewQuote @createNewQuote="newQuote"></appNewQuote>
    <appQuoteGrid :Quotes="quotes" @deleteQuote="deletefromParent"></appQuoteGrid>
    <div class="row">
      <div class="col">
        <div class="alert alert-info">
          Click on quote to delete it
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid'
import NewQuote from './components/NewQuote'
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  data() {
    return {
      quotes: [
        {
          text: 'Just a Quote to see something',
          author: 'John Doe'
        }
      ],
      maxQuotes: 10,
    }
  },
  methods: {
    newQuote(newQuote) {
      if(this.quotes.length >= this.maxQuotes) {
        return alert('Please delete Quotes first');
      }
      this.quotes.push(newQuote)
    },
    deletefromParent(index){
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
