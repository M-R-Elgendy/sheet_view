<template>
  <div class="col-12">
    <table class="table ">
      <thead class="thead-dark">
        <tr>
          <th v-for="colm in columns" :key="'colm_' + colm.caption">
            {{ colm["caption"] }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="row in rows" :key="'row_' + row.id">
          <td v-for="colmCap in columns" v-bind:key="colmCap.id">
            {{ row[colmCap["caption"]] }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: ["columns", "rows"],

  name: "dataTable"
};
</script>
