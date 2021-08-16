<template>
  <div class="d-flex flex-column ">
    <v-card min-height="600px" class="ma-4 pa-2 ">
      <v-card-text>
        <v-text-field
          label=" input"
          @focus="input"
          @blur="reset"
        ></v-text-field>
      </v-card-text>
    </v-card>

    <v-btn
      color="primary"
      :class="isbuttonsticky || 'mx-4'"
      :bottom="isbuttonsticky"
      :fixed="isbuttonsticky"
      :min-width="isbuttonsticky ? '100%' : none "
      max-width="100%"
    >
      <div class="font-weight-bold font-14" v-text="'Create Request'"></div>
    </v-btn>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isbuttonsticky:false,
    };
  },
  methods: {
    input() {
      if (this.$vuetify.breakpoint.xs) {
        this.isbuttonsticky=true
      }
    },
    reset() {
      this.isbuttonsticky=false
    }
  }
};
</script>

<style lang="scss" scoped>
.font-14{
  font-size: 14px;
  text-transform:none;
}
</style>
