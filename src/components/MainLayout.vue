<template>
  <a-layout id="components-layout-demo-fixed-sider">
    <a-layout-sider :style="{ overflow: 'auto', height: '100vh', position: 'fixed', left: 0 }">
      <div class="logo"></div>
      <a-menu theme="dark" mode="inline" :defaultSelectedKeys="['4']">
        <a-menu-item key="1">
          <a-icon type="user" />
          <span class="nav-text">Stacked Chart</span>
        </a-menu-item>
        <a-menu-item key="2">
          <a-icon type="video-camera" />
          <span class="nav-text">Bar Chart</span>
        </a-menu-item>
        <a-menu-item key="3">
          <a-icon type="upload" />
          <span class="nav-text">Line Chart</span>
        </a-menu-item>
        <a-menu-item key="4">
          <a-icon type="bar-chart" />
          <span class="nav-text">Bubble Chart</span>
        </a-menu-item>
      </a-menu>
    </a-layout-sider>
    <a-layout :style="{ marginLeft: '200px' }">
      <a-layout-header :style="{ background: '#fff', padding: 0 }" />
      <a-layout-content :style="{ margin: '24px 16px 0', overflow: 'initial' }">
        <a-row id="stackedChart">
          <div :style="{ padding: '24px', background: '#fff', textAlign: 'center' }">
            <StackedChart />
            <a-table :columns="columns" :dataSource="data" :scroll="{ x: 1300 }"></a-table>
          </div>
        </a-row>
        <a-row
          id="verticalBarChart"
          :style="{ padding: '24px', background: '#fff', textAlign: 'center' }"
        >
          <VerticalBar :styles="{height: '400px'}" />
        </a-row>
        <a-row id="lineChart" :style="{ padding: '24px', background: '#fff', textAlign: 'center' }">
          <LineChart :styles="{height: '300px'}" />
        </a-row>
        <a-row
          id="bubbleChart"
          :style="{ padding: '24px', background: '#fff', textAlign: 'center' }"
          :gutter="16"
        >
          <a-col class="gutter-row" :span="6">
            <a-card hoverable style="width: 300px">
              <img alt="example" src="../assets/tanny.svg" slot="cover" />

              <a-card-meta title="Tammy Abraham" description="England">
                <a-avatar slot="avatar" src="../assets/tanny.svg" />
              </a-card-meta>
            </a-card>
          </a-col>
          <a-col class="gutter-row" :span="18">
            <BubbleChart :styles="{height: '300px'}" />
          </a-col>
        </a-row>
      </a-layout-content>
      <a-layout-footer :style="{ textAlign: 'center' }">Sport Demo App</a-layout-footer>
    </a-layout>
  </a-layout>
</template>
<script>
import StackedChart from "./StackedColumnChart.vue";
import VerticalBar from "./VerticalBar.vue";
import LineChart from "./LineChart.vue";
import BubbleChart from "./BubbleChart.vue";

const columns = [
  { title: "", dataIndex: "name", key: "1" },
  { title: "Facebook", dataIndex: "amount", key: "2" },
  { title: "Instagram", dataIndex: "amount", key: "3" },
  { title: "Twitter", dataIndex: "amount", key: "4" },
  { title: "Youtube", dataIndex: "amount", key: "5" },
  { title: "Linkedin", dataIndex: "amount", key: "6" },
  { title: "Snapchat", dataIndex: "amount", key: "7" },
  { title: "Average", dataIndex: "amount", key: "8" },
  { title: "Total", dataIndex: "amount", key: "9" }
];

const data = [
  {
    key: "1",
    name: "Text",
    amount: "$12,453,75",
    address: "New York Park"
  },
  {
    key: "2",
    name: "Photo",
    amount: "$12,453,75",
    address: "London Park"
  },
  {
    key: "3",
    name: "Video",
    amount: "$12,453,75",
    address: "New York Park"
  },
  {
    key: "4",
    name: "Total",
    amount: "$12,453,75",
    age: 40,
    address: "London Park"
  }
];
export default {
  name: "MainLayout",
  components: {
    StackedChart,
    VerticalBar,
    LineChart,
    BubbleChart
  },
  data() {
    return {
      data,
      columns
    };
  }
};
</script>
<style>
#components-layout-demo-fixed-sider .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px;
}
</style>