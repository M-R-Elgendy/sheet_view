<template>
  <div class="col-12">
    <table class="table ">
      <thead class="thead-dark">
        <tr>
          <th v-for="colm in columns" :key="colm">
            {{ colm["caption"] }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="row in rows" :key="row.id">
          <td v-for="me in columns" v-bind:key="me.id">
            {{ row[me["caption"]] }}
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
