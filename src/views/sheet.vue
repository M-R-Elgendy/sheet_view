<template>
  <div class="sheet">
    <div id="nav">
      <!-- <router-link to="/">Home</router-link> | -->
      <router-link to="/sheet">Sheet view</router-link>
    </div>

    <div class="container">
      <div class="row">
        <div class="col-12">
          <sheetProperties
            :uuid="uuid"
            :name="name"
            :description="description"
            :documentation="documentation"
            :icon="icon"
            :themeColor="themeColor"
            :createdBy="createdBy"
            :createdOn="createdOn"
          />
          <br />
          <dataTable :columns="columns" :rows="rows" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import sheetProperties from "@/components/sheetProperties.vue";
import dataTable from "@/components/dataTable.vue";

import JsonFile from "../json/workbase-schema.json";
import RowFile from "../json/sheetRows.json";

export default {
  mounted() {
    if (!localStorage.user_name) {
      alert("no User name, Plz log in first");
      window.location.href = "../"
    }
  },

  data: function() {
    return {
      uuid: JsonFile["uuid"],
      name: JsonFile["name"],
      description: JsonFile["description"],
      documentation: JsonFile["documentation"],
      icon: JsonFile["icon"],
      themeColor: JsonFile["themeColor"],
      createdBy: JsonFile["createdBy"],
      createdOn: JsonFile["createdOn"],
      columns: JsonFile["schema"]["worktables"]["employees"]["columns"],

      rows: RowFile
    };
  },

  components: {
    sheetProperties,
    dataTable
  }
};
</script>
