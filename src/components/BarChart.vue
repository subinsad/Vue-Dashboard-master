<template>
  <canvas ref="barChart" style="width: 140px; height: 140px" />
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
            "#1A4568",
            "#90AFC4",
            "#D9D9D9",
            "rgba(75, 192, 192, 0.2)",
          ],

          borderWidth: 0,
        },
      ],
    },
    options: {
      scales: {
        y: {
          beginAtZero: true,
          grid: {
            drawBorder: false,
            display: false,
            drawTicks: false,
          },
        },

        x: {
          grid: {
            drawBorder: false,
            display: false,
            drawTicks: false,
          },
        },
      },

      plugins: {
        legend: {
          display: false,
        },
      },

      legend: {
        display: false,
      },
      responsive: false,
      scales: {
        xAxes: [
          {
            stacked: true,
          },
        ],
      },

      cutout: "80%",
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
