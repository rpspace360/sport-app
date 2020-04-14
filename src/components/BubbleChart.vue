<script>
import { Bubble } from "vue-chartjs";
export default {
  extends: Bubble,
  name: "BubbleChart",
  watch: {
    chartData() {
      this.updateChart();
    }
  },

  mounted() {
    this.render();
  },
  methods: {
    updateChart() {
      // Destroy method needed for avoiding a bug in chart js when you hover over chart
      // and old chart from previous render displayed
      if (this.$data._chart) this.$data._chart.destroy();
      this.render();
    },
    render() {
      this.renderChart(
        {
          labels: ["Data"],
          datasets: [
            {
              label: ["Team"],
              backgroundColor: ["yellow", "green", "red", "blue", "grey", "pink", "purple", "orange", "yellow"],
              pointBackgroundColor: "white",
              borderWidth: 1,
              pointBorderColor: "#249EBF",
              data: [
                {
                  x: 40,
                  y: 43,
                  r: 20
                },
                {
                  x: 43,
                  y: 41,
                  r: 10
                },
                {
                  x: 45,
                  y: 43,
                  r: 60
                },
                {
                  x: 40,
                  y: 43,
                  r: 30
                },
                {
                  x: 49,
                  y: 40,
                  r: 20
                },
                {
                  x: 39,
                  y: 51,
                  r: 25
                },
                {
                  x: 40,
                  y: 45,
                  r: 50
                },
                {
                  x: 45,
                  y: 35,
                  r: 25
                },
                {
                  x: 40,
                  y: 40,
                  r: 36
                }
              ]
            }
          ]
        },
        {
          scales: {
            yAxes: [
              {
                ticks: {
                  beginAtZero: true,
                   display: false
                },
                gridLines: {
                  display: false
                }
              }
            ],
            xAxes: [
              {
                ticks: {
                  beginAtZero: true,
                   display: false
                },
                gridLines: {
                  display: false
                }
              }
            ]
          },
          legend: {
            display: false
          },
      
          responsive: true,
          maintainAspectRatio: false,
          height: 200,
          width: 100
        }
      );
    }
  }
};
</script>
