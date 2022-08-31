<script setup>
import { ref } from 'vue';

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <table>
    <tr>
      <th>Model #</th>
      <td v-for="model in prodsObj" :key="model.Model">
        {{ model.Model }}
      </td>
    </tr>
    <tr>
      <th>Hair Types</th>
      <td v-for="model in prodsObj" :key="model.Model">
        {{ model.HairTypes }}
      </td>
    </tr>
    <tr>
      <th>No Heat Damage</th>
      <td v-for="model in prodsObj" :key="model.Model">
        {{ model.NoHeatDamage }}
      </td>
    </tr>
    <tr>
      <th>Ultra-Fast Drying</th>
      <td v-for="model in prodsObj" :key="model.Model">
        {{ model.UltraFastDrying }}
      </td>
    </tr>
    <tr>
      <th>IQ 2-in-1 Concentrator</th>
      <td v-for="model in prodsObj" :key="model.Model">
        {{ model.IQConcentrator }}
      </td>
    </tr>
  </table>
</template>
<script>
import prodCompare from '../assets/products.json';

export default {
  data() {
    return {
      prodsObj: prodCompare,
    };
  },
};
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
table,
th,
td {
  border: 1px solid black;
  border-collapse: collapse;
}
table {
  width: 100%;
}
td th {
  width: 25%;
}
</style>
