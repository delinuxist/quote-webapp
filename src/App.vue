<template>
  <div class="container">
    <appHeader :maxQuotes="maxQuotes" :quoteCount="quotes.length"></appHeader>
    <newQuote @quoteAdded="newQuote"></newQuote>
    <quoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></quoteGrid>

    <div class="row mt-5">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to Delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";
export default {
  data: function () {
    return {
      quotes: ["Just a Quote to see something"],
      maxQuotes: 10,
    };
  },
  components: {
    quoteGrid: QuoteGrid,
    newQuote: NewQuote,
    appHeader: Header,
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please Delete Quotes first!");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
};
</script>

<style>
</style>
