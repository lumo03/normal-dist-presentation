<script lang="ts">
import { Chart as ChartJS, registerables } from "chart.js";
import { Line } from "vue-chartjs";

ChartJS.register(...registerables);

export default {
  name: "LineChart",
  components: { Line },
  data() {
    return {
      mu: 0,
      sigma: 1,
      chartOptions: {
        responsive: true,
        radius: 0,
        animation: false,
      },
    };
  },
  computed: {
    chartDataLabels() {
      return Array.from({ length: 201 }, (_, i) => (i / 10 - 10).toFixed(1));
    },
    chartDatasetLabel() {
      return `N(${(this.mu * 1).toFixed(2)}|${(this.sigma * this.sigma).toFixed(2)})`;
    },
    chartData() {
      let data: number[] = [];
      this.chartDataLabels.forEach((x) => {
        data.push(
          Math.exp(-0.5 * Math.pow((x - this.mu) / this.sigma, 2)) /
            Math.sqrt(2 * Math.PI) /
            this.sigma
        );
      });
      console.log(data);
      return {
        labels: this.chartDataLabels,
        datasets: [{ data, label: this.chartDatasetLabel }],
      };
    },
  },
};
</script>

<template>
  <h1>Graph</h1>
  <div id="content">
    <Line id="line-chart" :options="chartOptions" :data="chartData" />
    <div class="input-fields">
      <div class="mu-input">
        <label for="mu">Wert für Mu:</label>
        <input
          v-model="mu"
          type="range"
          id="mu"
          min="-10"
          max="10"
          step="0.1"
        />
        <span id="mu-value">{{ mu }}</span>
      </div>
      <br />
      <br />
      <div class="sigma-input">
        <label for="sigma">Wert für Sigma:</label>
        <input
          v-model="sigma"
          type="range"
          id="sigma"
          min="-1"
          max="10"
          step="0.1"
        />
        <span id="sigma-value">{{ sigma }}</span>
      </div>
    </div>
  </div>
</template>

<style>
#content {
  display: flex;
  flex-direction: row;
  height: 100%;
  width: 100%;
  justify-content: space-between;
}

#line-chart {
  max-width: 700px;
}

.input-fields {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  max-width: 400px;
}

.sigma-input,
.mu-input {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
