<template>
    <div class="about">
      <Events/>
        <h3>About Section</h3>
        <p>This is vuejs crash course by Brad Traversy</p>
        <h1>Area Chart</h1>
        <DrawAreaChart
        @select="onSelect"
        :data="data"
        :ceil="max"
        class="area-chart" />
        <div class="content">
        <h3>Selected Value: {{currentValue}}</h3>
        <div>
            <label>Record Count: </label>
            <input v-model:value="itemCount" />
        </div>
        <div>
            <label>Min Value: </label>
            <input v-model:value="min" />
        </div>
        <div>
            <label>Max Value: </label>
            <input v-model:value="max" />
        </div>
        </div>

        <DrawChart/>
        <DrawLineChart/>

    </div>
</template>

<script>
import DrawChart from '../components/DrawChart'
import DrawLineChart from '../components/DrawLineChart'
import DrawAreaChart from '../components/DrawAreaChart'
import AreaData from '../data.js'

import Events from '../components/Events'
export default {
   
    data() {
    return {
      data: [],
      chartWidth: 0,
      currentValue: null,
      itemCount: 25,
      min: 10,
      max: 100,
    };
  },
  mounted() {
    setInterval(() => {
      this.data = AreaData(this.itemCount,
        parseInt(this.min, 10),
        parseInt(this.max, 10));
    }, 2000);
  },
  methods: {
    onSelect(value) {
      this.currentValue = value;
    },
  },
   components: {
        DrawChart,
        DrawLineChart,
        DrawAreaChart,
        Events
    }
};
</script>

<style scoped>
 .about {
     text-align: center;
 }
</style>
