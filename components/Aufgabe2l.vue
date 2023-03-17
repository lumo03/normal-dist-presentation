<script lang="ts">
import LatexExpression from "./latex-expression.vue";
const le = LatexExpression;
export default {
  components: {
    le,
  },
};
</script>

<template>
  <h1>Lösung</h1>
  <br />
  <v-clicks>
    <ol class="list-upper-alpha">
      <li>
        <le ex="P(x > 3000)=0,699" />; <le ex="P(x < 2500)=0,082" />;
        <le ex="P(4000 \leq X \leq 5000)=0,110" />
      </li>
      <br />
      <br /> 
      <li><le ex="3896" /> g; <le ex="2912" /> g</li>
      <br />
      <li><le ex="2354" /> g; <le ex="4246" /> g</li>
    </ol>
  </v-clicks>
</template>
