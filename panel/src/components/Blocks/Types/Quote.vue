<template>
  <div class="k-block-type-quote-editor">
    <k-writer
      ref="text"
      :inline="true"
      :placeholder="textField.placeholder"
      :value="content.text"
      class="k-block-type-quote-text"
      @input="update({ text: $event })"
    />
    <k-writer
      ref="citation"
      :inline="true"
      :placeholder="citationField.placeholder"
      :value="content.citation"
      class="k-block-type-quote-citation"
      @input="update({ citation: $event })"
    />
  </div>
</template>

<script>
/**
 * @displayName BlockTypeQuote
 * @internal
 */
export default {
  computed: {
    citationField() {
      return this.field("citation", {});
    },
    textField() {
      return this.field("text", {});
    }
  },
  methods: {
    focus() {
      this.$refs.text.focus();
    }
  }
};
</script>

<style lang="scss">
.k-block-type-quote-editor {
  padding-left: 1rem;
  border-left: 2px solid #000;
}
.k-block-type-quote-text {
  font-size: $text-xl;
  margin-bottom: .25rem;
  line-height: 1.25em;
}
.k-block-type-quote-citation {
  font-style: italic;
  font-size: $text-sm;
  color: $color-gray-600;
}
</style>
