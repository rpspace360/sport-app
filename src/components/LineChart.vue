<script>
import { Line } from "vue-chartjs";
export default {
  extends: Line,
  name: "LineChart",
   watch: {
    chartData() {
      this.updateChart();
    },
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
      
    this.renderChart({
      labels: ['Chelsea', 'Manchester United', 'Sprus', 'Arsenal', 'Barcelona'],
      datasets: [
        {
          label: '',
          barThickness: 50,
        
          backgroundColor: ["#C1FF84"] ,
          data: [40, 20, 12, 39, 20]
        },
      ],
    
 
    },
    {
                    maintainAspectRatio: false,
                    responsive: true,
                     legend: {
            display: false
          },
           animation: {
            duration: 0,
            onComplete: function() {
              let currentChart = this.chart;
              let ctx = currentChart.ctx;

              // style for arrow indicator
              ctx.font = "14px 'Helvetica Neue', Helvetica, Arial, sans-serif";
              this.data.datasets.forEach((dataset, index) => {
                let meta = currentChart.controller.getDatasetMeta(index);
                meta.data.map(bar => {
                      let yourImage = new Image();
                         

                      yourImage.onload = function(){
                    let calculatedXOffset =
                      bar._model.base - ctx.measureText(`${bar._model.label}`).width - 30;
                    let xOffset = calculatedXOffset < 0 ? 0 : calculatedXOffset;
                    let yOffset = bar._model.y + 5;

                    ctx.fillStyle = "rgba(157, 112, 177, 0.85)";
                   
                 
                    this.repeatCallback
                      ? ctx.drawImage(yourImage, xOffset, yOffset - 13)
                      : ctx.drawImage(yourImage, xOffset, yOffset);
                      }
                       yourImage.src = '../assets/logo.png'
                });
              });
              this.repeatCallback = true;
            }
          },
   
                    scales: {
            xAxes: [
              {
                display: true,
                 gridLines: {
                  display: false
                },
                
              
              }
            ],
            yAxes: [
              {
                display: true,
                barPercentage: 1,
               
               
              
              }
            ]
          }
                })

    }
  }
};
</script>
