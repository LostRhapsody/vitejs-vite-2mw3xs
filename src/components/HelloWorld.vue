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
      <th>
        Compare Hair Dryers
        <p>
          To start over, or to view all available products, click the
          <strong>Reset</strong> button.
        </p>
        <button
          style="
            color: black;
            border: solid black 0.1em;
            border-radius: 0 0 0 0;
          "
        >
          Reset
        </button>
      </th>
      <td v-for="model in prodsObj" :key="model.Model">
        <span v-html="model.card.img"></span>
      </td>
    </tr>
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
