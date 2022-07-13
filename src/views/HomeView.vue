<template>
  <v-img src="../assets/background_thinking.png">
    <v-container>
      <v-row justify="center">
        <v-col>
          <v-img class="mx-auto" src="../assets/image_copilot.png" width="1000"></v-img>
        </v-col>
      </v-row>
      <page-index />
    </v-container>
  </v-img>
</template>

<script>
  import PageIndex from "@/components/PageIndex";

  export default {
    name: 'HomeView',

    components: {
      PageIndex,
    },
  }
</script>
