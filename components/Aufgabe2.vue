<script lang="ts">
 import LatexExpression from './latex-expression.vue';
  const le = LatexExpression;
  export default {
  components: {
   le
  }
};
</script>

<template>
  <h1>Aufgabe 2</h1>
  Das Gewicht von neugeborenen Kindern in Deutschland ist annähernd normalverteilt mit 
  <le ex="\mu = 3300"/> g und <le ex="\sigma = 575"/> g.
  <ol class="list-upper-alpha e">
  <li>
    Berechne die Wahrscheinlichkeit, dass ein Neugeborenes
    <ul>
      <li>mehr als <le ex="3000"/> g wiegt,</li>
      <li>weniger als <le ex="2500"/> g wiegt,</li>
      <li>zwischen <le ex="4000"/> g und <le ex="5000"/> g wiegt.</li>
    </ul>
  </li>
  <li>
    Wie schwer muss ein Neugeborenes sein, damit es
    <ul>
      <li>zu den <le ex="15 \%"/> schwersten,</li>
      <li>zu den <le ex="25 \%"/> leichtesten gehört?</li>
    </ul>
  </li>
  <li>
    In welchem um <le ex="\mu"/> symmetrischen Bereich liegen die Gewichte von <le ex="90 \%"/> aller Neugeborenen?
  </li>
</ol>
</template>