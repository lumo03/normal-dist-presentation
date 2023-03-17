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
  <v-clicks>
    <ol class="list-upper-alpha">
      <li>
        Erfüllte Voraussetzungen für Bernoulli-Experiment:
        <ul>
          <li>
            Pro Würfeln zwei mögliche Ereignisse ("eine Sechs", "keine Sechs")
          </li>
          <li>
            Die Wahrscheinlichkeiten für das Würfeln von Sechsen sind unabhängig
            voneinander
          </li>
        </ul>
      </li>
      <li>Die Zufallsgröße ist hier diskret und nicht stetig.</li>
      <li>
        <le
          ex="P_B(100\leq S_{n}\leq 150)=\sum _{{i=100}}^{{150}}{\binom  {1000}{i}}p^{i}(1-p)^{{1000-i}}=\text{binomcdf}(1000, 1/6, 100, 150) \approx 0{,}0837"
        />
      </li>
      <li>
        ja, denn <le ex="\sigma^2 \approx 138,889 > 9" /> und ist groß (<le
          ex="n = 1000"
        />)
      </li>
      <li>
        <le
          ex="P_N(100\leq S_{n}\leq 150)=\text{normcdf}(100-0,5; 150+0,5; \frac{1000}{6}, \sqrt{138,9}) \approx 0{,}0851 "
        />
      </li>
    </ol>
  </v-clicks>
</template>
