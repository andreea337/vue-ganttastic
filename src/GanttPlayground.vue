<template>
 <g-gantt-chart
      chart-start="2024-01-01"
      chart-end="2024-12-31"
      precision="month"
      bar-start="myBeginDate"
      bar-end="myEndDate"
      date-format="YYYY-MM-DD"
      color-scheme="vue"
      :current-time="true"
      current-time-label="現在"
      :no-overlap="true"
      :grid="true"
      :row-height="60"
      label-column-title="SYSTEM"
      >
      <!-- <g-gantt-row
        v-for="(row, index) in rawdata"
        :key="`${row.label}`+ index"
        :label="row.label"
        :bars="row.bars"
        :highlight-on-hover="true"
        :labelstyle="titleStyle"
      /> -->
      <g-gantt-row label="PLM系統基本架構" :bars="row1BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="APQP" :bars="row2BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="APQP * WBS" :bars="row3BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="KPI" :bars="row4BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="CSR" :bars="row5BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="PDM" :bars="row6BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="PDM * QSR AI" :bars="row7BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="RM" :bars="row8BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="PPAP" :bars="row9BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="PRA" :bars="row10BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="ECR 整合" :bars="row20BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="ECR" :bars="row11BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="ECN" :bars="row12BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="CAR" :bars="row13BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="MES\ERP 整合" :bars="row20BarList" :highlight-on-hover="true" :labelstyle="titleStyle"/>
      <g-gantt-row label="DS" :bars="row14BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="SUA" :bars="row15BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
      <g-gantt-row label="PPM" :bars="row16BarList" :highlight-on-hover="true" :labelstyle="subStyle"/>
    </g-gantt-chart>
</template>

<script setup lang="ts">
import { ref } from "vue"
import type { GanttBarObject } from "./types"
import dayjs from "dayjs"
import data from "./data.json"

const subStyle = ref({
    backgroundColor: "white"
});
const titleStyle = ref({
    justifyContent: "start", backgroundColor: "#E5E5E5", paddingLeft: "20px"
});
// border: "1px solid #c1c1c1",
const rawdata = ref(data as any);
console.log(rawdata.value)
const row20BarList = ref([
{
    myBeginDate: "2025-01-01",
    myEndDate: "2025-03-01",
    ganttBarConfig: {
        id: "bar2",
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row1BarList = ref([
{
    myBeginDate: "2024-01-01",
    myEndDate: "2024-02-01",
    ganttBarConfig: {
        id: "bar1", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
// row1BarList.value.push({
//     myBeginDate: "2024-05-01",
//     myEndDate: "2024-07-01",
//     ganttBarConfig: {
//         id: "bar20", 
//         label: "100%",
//         hasHandles: true,
//         style: {
//             background: "#00bf63",
//         }
//     }
// });
const row2BarList = ref([
{
    myBeginDate: "2024-01-01",
    myEndDate: "2024-03-01",
    ganttBarConfig: {
        id: "bar2",
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row3BarList = ref([
{
    myBeginDate: "2024-04-15",
    myEndDate: "2024-07-01",
    ganttBarConfig: {
        id: "bar3", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row4BarList = ref([
{
    myBeginDate: "2024-03-01",
    myEndDate: "2024-05-01",
    ganttBarConfig: {
        id: "bar4", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row5BarList = ref([
{
    myBeginDate: "2024-04-01",
    myEndDate: "2024-06-01",
    ganttBarConfig: {
        id: "bar5", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row6BarList = ref([
{
    myBeginDate: "2024-05-01",
    myEndDate: "2024-07-15",
    ganttBarConfig: {
        id: "bar6", 
        label: "80%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "linear-gradient(90deg, #00bf63 0%, #00bf63 80%, #1b794c 80%, #1b794c 100%)",
        }
    }
}]);
const row7BarList = ref([
{
    myBeginDate: "2024-07-01",
    myEndDate: "2024-12-31",
    ganttBarConfig: {
        id: "bar7", 
        label: "20%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "linear-gradient(90deg, #ffde59 0%, #ffde59 20%, #ffbd59 20%, #ffbd59 100%)",
        }
    }
}]);
const row8BarList = ref([
{
    myBeginDate: "2024-06-01",
    myEndDate: "2024-07-20",
    ganttBarConfig: {
        id: "bar8", 
        label: "80%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "linear-gradient(90deg, #ffde59 0%, #ffde59 80%, #ffbd59 80%, #ffbd59 100%)",
        }
    }
}]);
const row9BarList = ref([
{
    myBeginDate: "2024-06-01",
    myEndDate: "2024-07-20",
    ganttBarConfig: {
        id: "bar9", 
        label: "80%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "linear-gradient(90deg, #ffde59 0%, #ffde59 80%, #ffbd59 80%, #ffbd59 100%)",
        }
    }
}]);
const row10BarList = ref([
{
    myBeginDate: "2024-10-01",
    myEndDate: "2024-12-31",
    ganttBarConfig: {
        id: "bar10", 
        label: "0%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#d9d9d9",
        }
    }
}]);
const row11BarList = ref([
{
    myBeginDate: "2024-07-15",
    myEndDate: "2024-11-01",
    ganttBarConfig: {
        id: "bar11", 
        label: "5%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "linear-gradient(90deg, #ffde59 0%, #ffde59 5%, #ffbd59 5%, #ffbd59 100%)",
        }
    }
}]);
const row12BarList = ref([
{
    myBeginDate: "2024-01-01",
    myEndDate: "2024-07-01",
    ganttBarConfig: {
        id: "bar12", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row13BarList = ref([
{
    myBeginDate: "2024-04-15",
    myEndDate: "2024-06-01",
    ganttBarConfig: {
        id: "bar13", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row14BarList = ref([
{
    myBeginDate: "2024-01-01",
    myEndDate: "2024-03-01",
    ganttBarConfig: {
        id: "bar14", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row15BarList = ref([
{
    myBeginDate: "2024-01-01",
    myEndDate: "2024-05-01",
    ganttBarConfig: {
        id: "bar15", 
        label: "100%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#00bf63",
        }
    }
}]);
const row16BarList = ref([
{
    myBeginDate: "2024-09-01",
    myEndDate: "2024-11-01",
    ganttBarConfig: {
        id: "bar16", 
        label: "0%",
        // hasHandles: true,
        immobile: true,
        style: {
            background: "#d9d9d9",
        }
    }
}]);

</script>

<style scoped lang="scss">
:deep(.g-timeunits-container) {
    width: auto;
    .g-timeunit{
        flex: 1;
        font-size: 1rem;
    }
    @media screen and (max-width: 1644px) {
        .g-timeunit{
            font-size: 0.8rem;
        }
    }
    @media screen and (max-width: 768px) {
        .g-timeunit{
            font-size: 0.5rem;
        }
    }
}

:deep(.g-gantt-rows-container) {
    .g-gantt-row {
        .g-gantt-row-label{
            font-size: 1.2rem;
            padding: 1rem;
        }
        .g-gantt-bar-label{
            display: flex;
            justify-content: flex-end;
            color: white;
            margin-right: 5px;
        }
    }
}

:deep(.g-label-column){
  // width: 300px !important; src\components\GGanttChart.vue -> labelColumnWidth
    .g-label-column-header{
        font-size: 1.2rem;
        font-weight: bold;
    }
    .g-label-column-rows{
        font-size: 1rem;
        // background: #E5E5E5 !important; 
        .g-label-column-row{
            color: black;
            font-weight: 600;
            // border: 1px solid #c1c1c1;
        }
    }
}

:deep(.g-labelgrid-column){
  // width: 300px !important; src\components\GGanttChart.vue -> labelColumnWidth
    .g-label-column-header{
        font-size: 1.2rem;
        font-weight: bold;
    }
    .g-label-column-rows{
        font-size: 1rem;
        // background: #E5E5E5 !important; 
        .g-label-column-row{
            color: black;
            font-weight: 600;
            // border: 1px solid #c1c1c1;
        }
    }
}
</style>