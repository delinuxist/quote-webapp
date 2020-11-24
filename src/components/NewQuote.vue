<template>
  <div class="row mt-5">
    <div class="col-sm-8 col-7 mx-auto">
      <form>
        <div class="form-group">
          <label class="font-weight-bolder">Quote</label>
          <textarea class="form-control" rows="3" v-model="quote"></textarea>
        </div>
      </form>
    </div>

    <div class="col-sm-8 col-7 mx-auto">
      <form>
        <div class="form-group">
          <button class="btn btn-primary" @click.prevent="createNew">
            Add Quote
          </button>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      quote: "",
    };
  },
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    },
  },
};
</script>
<style>
</style>