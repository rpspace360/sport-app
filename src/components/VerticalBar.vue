<script>
import { Bar } from "vue-chartjs";
import hyandai from '@/assets/hyandai.svg'
export default {
  extends: Bar,
  name: "VerticalChart",

  mounted() {
    this.render();
  },
  methods: {
    render() {
       let yourImage = new Image();
       yourImage.src = hyandai
      
    this.renderChart({
      labels: ['Hyundai', 'Hublot', 'Fiserv', 'EA Sports', 'Airtel', 'Nike', 'Beeline', 'Chevrolet', 'Bwin', 'Singha'],
      datasets: [
        {
          label: '',
          barThickness: 50,
          pointRadius: 20,
        pointHoverRadius: 20,
        pointHitRadius: 20,
        pointStyle: yourImage,
        
          backgroundColor: ["red", "blue", "green", "orange", "pink", "purple", "yellow", "grey", "voilet", "red"] ,
          data: [40, 20, 12, 39, 20, 40, 39, 80, 40, 20]
        }
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
              // let currentChart = this.chart;
              // let ctx = currentChart.ctx;

              // // style for arrow indicator
              // ctx.font = "14px 'Helvetica Neue', Helvetica, Arial, sans-serif";
              // this.data.datasets.forEach((dataset, index) => {
              //   let meta = currentChart.controller.getDatasetMeta(index);
              //   meta.data.map(bar => {
              //         let yourImage = new Image();
                         

              //         yourImage.onload = function(){
              //     // setting postion of arrow "➡" inside canvas on left site of current placement
                
              //       // calculating  x coordinate for arrow ➡ relative to the canvas by substracting current placement name widht from base width
              //       let calculatedXOffset =
              //         bar._model.base - ctx.measureText(`${bar._model.label}`).width - 30;
              //       let xOffset = calculatedXOffset < 0 ? 0 : calculatedXOffset;
              //       let yOffset = bar._model.y + 5;

              //       ctx.fillStyle = "rgba(157, 112, 177, 0.85)";
                   
              //       // fix for repeatative update of canvas object on hover on bar to set exact position of arrow "➡" in left of current placement name tick
              //       this.repeatCallback
              //         ? ctx.drawImage(yourImage, xOffset, yOffset - 13)
              //         : ctx.drawImage(yourImage, xOffset, yOffset);
              //         }
              //          yourImage.src = hyandai;
              //          yourImage.height = "20px"
              //          yourImage.width = "20px";
              //   });
              // });
              // this.repeatCallback = true;
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
