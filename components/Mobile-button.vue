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
      :class="button_size"
      :bottom="bottom"
      :fixed="mobilefocused"
      max-width="100%"
      :min-width="minwidth"
    >
      <div class="font-weight-bold font-14">Create Request</div>
    </v-btn>
  </div>
</template>
<script>
export default {
  data() {
    return {
      mobilefocused: false,
      button_size: "mx-4 pa-2 ",
      bottom: false,
      minwidth: "1%"
    };
  },
  methods: {
    input() {
      if (this.$vuetify.breakpoint.xs) {
        this.button_size = this.button_size.substring(4);
        this.mobilefocused = true;
        this.bottom = true;
        this.minwidth = "100%";
      }
    },
    reset() {
      this.button_size = "mx-4 pa-2";
      this.mobilefocused = false;
      this.bottom = false;
      this.minwidth = "1%";
    }
  }
};
</script>

<style lang="scss" scoped>
.font-14 {
  font-size: 14px;
}
</style>
