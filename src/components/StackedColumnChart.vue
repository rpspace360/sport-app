<script>
import { Bar } from "vue-chartjs";
import pattern from "patternomaly"
export default {
  extends: Bar,
  name: "StackedChart",
  props: [
    "chartData",
    "metric",
    "currentCurrency",
    "currentPlacement",
    "currentPlacementIndex",
    "chartSettings"
  ],
  mounted() {
    this.render();
  },
  methods: {
    render() {
    

   this.renderChart({
      labels: ['Facebook', 'Instagram', 'Twitter', 'YouTube', 'Linkedin', 'SnapChat'],
      datasets: [
        {
          label: 'Text',
          backgroundColor: pattern.draw('diagonal', '#3D5B96'),
          data: [40, 39, 10, 40, 39, 80]
        },
        {
          label: 'Video',
          backgroundColor: pattern.draw('diagonal', '#f87979'),
          data: [40, 39, 10, 40, 39, 80]
        },
         {
          label: 'Image',
          backgroundColor: pattern.draw('diagonal', '#1EFFFF'),
          data: [20, 10, 12, 33, 22, 4]
        }
      ]
    }, {
      responsive: true, 
      maintainAspectRatio: false,
      scales: {
        xAxes: [{
          stacked: true,
          categoryPercentage: 0.5,
          barPercentage: 1
        }],
        yAxes: [{
          stacked: true
        }]
      }
    })
    }
  }
};
</script>
