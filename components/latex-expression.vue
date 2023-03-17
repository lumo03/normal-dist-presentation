<template>
    <span v-html="renderedExpression"></span>
</template>

<script>
import katex from 'katex';

export default {
  props: {
    ex: {
      type: String,
      required: true
    }
  },
  computed: {
    renderedExpression() {
      try {
        return katex.renderToString(this.ex);
      } catch (error) {
        console.error(error);
        return '';
      }
    }
  }
};
</script>