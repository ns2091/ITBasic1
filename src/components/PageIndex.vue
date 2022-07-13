<template>
  <v-container id="cards">
    <v-row justify="center">
      <v-col cols="4">
        <a href="ReportBody.pdf"><v-img src="../assets/button_report.png" width="400" class="mx-auto"></v-img></a>
      </v-col>
      <v-col cols="4">
        <router-link to="/presentation"><v-img src="../assets/button_presentation.png" width="400" class="mx-auto"></v-img></router-link>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "PageIndex",
  data() {
    return {
      cardBody: [
        {

        }
      ]
    }
  }
}
</script>

<style scoped>

</style>