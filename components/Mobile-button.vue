<template>
  <div class="d-flex flex-column stickybutton-container">
    <v-card min-height="600px" class="mx-4 pa-2 ">
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
      :class="isbuttonsticky && 'justify-end' || 'ma-4'"
      :fixed="isbuttonsticky"
      :min-width="isbuttonsticky ? '100%' : '1%' "
      :tile='isbuttonsticky'
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
.stickybutton-container{
  .v-btn{
    bottom:0px;
    .font-14{
      font-size: 14px;
      text-transform:none;
    }
  }
}
</style>
