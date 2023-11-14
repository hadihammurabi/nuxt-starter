<script lang="ts" setup>

const sheetBottomProfileShow = ref(false);
const onSheetBottomProfileToggle = () => {
  sheetBottomProfileShow.value = !sheetBottomProfileShow.value;
};

const sheetBottomNotifShow = ref(false);
const onSheetBottomNotifToggle = () => {
  sheetBottomNotifShow.value = !sheetBottomNotifShow.value;
};

import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'
import SheetBottomNotification from '~/components/SheetBottomNotification.vue';

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

const chartData = {
  labels: [
    'January',
    'February',
    'March',
    'April',
    'May',
    'June',
    'July',
    'August',
    'September',
    'October',
    'November',
    'December'
  ],
  datasets: [
    {
      label: 'Data One',
      backgroundColor: '#f87979',
      data: [40, 20, 12, 39, 10, 40, 39, 50, 40, 20, 12, 11]
    }
  ]
}

const chartOptions = {
  responsive: true,
  maintainAspectRatio: false
}
</script>

<template>
  <BarTop @profile-click="onSheetBottomProfileToggle" @notif-click="onSheetBottomNotifToggle" />
  <h1>Dashboard</h1>

  <SheetBottomProfile :show="sheetBottomProfileShow" @close="onSheetBottomProfileToggle" />
  <SheetBottomNotification :show="sheetBottomNotifShow" @close="onSheetBottomNotifToggle" />

  <BCard v-for="i in 5" :key="i" class="pt-5">
    <BCardContent>
      <Bar
        id="chart"
        :options="chartOptions"
        :data="chartData"
      />
    </BCardContent>
  </BCard>

</template>

<style scoped>
#chart {
  width: 100% !important;
  height: 400px !important;
}
</style>
