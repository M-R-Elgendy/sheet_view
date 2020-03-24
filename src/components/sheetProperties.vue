<template>
  <div class="row col-12">
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
      user_Name: ""
    };
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
