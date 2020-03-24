<template>
  <div class="row col-12">
    <div class="col-12 text-left">
      <h2 class="text-left">Welcome: {{ userName }}</h2>
      <br />
    </div>
    <div calss="col-6 text-left" style="flex:auto; text-align:left;">
      <p>Sheet uuid: {{ uuid }}</p>
      <p>Sheet name: {{ name }}</p>
      <p>Sheet description: {{ description }}</p>
      <p>Sheet documentation: {{ documentation }}</p>
    </div>

    <div calss="col-6 text-left" style="flex:auto; text-align:left;">
      <p>Sheet icon: {{ icon }}</p>
      <p>Sheet themeColor: {{ themeColor }}</p>
      <p>Sheet createdBy: {{ createdBy }}</p>
      <p>Sheet createdOn: {{ createdOn }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      userName: ""
    };
  },

  mounted() {
    if (localStorage.user_name) {
      this.userName = localStorage.user_name;
    }
  },
  props: [
    "uuid",
    "name",
    "description",
    "documentation",
    "icon",
    "themeColor",
    "createdBy",
    "createdOn"
  ],

  name: "sheetProperties"
};
</script>
