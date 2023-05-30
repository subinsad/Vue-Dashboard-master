<template>
  <div>
    <canvas ref="barChart" style="width: 200px; height: 200px" />
  </div>
</template>

<script>
import { Chart, registerables } from "chart.js";
Chart.register(...registerables);

export default {
  data: () => ({
    type: "doughnut",
    data: {
      labels: ["A구역", "B구역", "C구역", "D구역"],
      datasets: [
        {
          label: "# of Votes",
          data: [12, 19, 3, 5],
          backgroundColor: [
            "rgba(255, 99, 132, 0.2)",
            "rgba(54, 162, 235, 0.2)",
            "rgba(255, 206, 86, 0.2)",
            "rgba(75, 192, 192, 0.2)",
          ],
          borderColor: [
            "rgba(255, 99, 132, 1)",
            "rgba(54, 162, 235, 1)",
            "rgba(255, 206, 86, 1)",
            "rgba(75, 192, 192, 1)",
          ],
          borderWidth: 1,
        },
      ],
    },
    options: {
      scales: {
        y: {
          beginAtZero: true,
        },
      },
    },
  }),
  mounted() {
    this.createChart();
  },
  methods: {
    createChart() {
      new Chart(this.$refs.barChart, {
        type: "doughnut",
        data: this.data,
        options: this.options,
      });
    },
  },
};
</script>
