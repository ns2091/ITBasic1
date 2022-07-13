<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="8">
        <v-card-title class="text-h1 font-weight-bold">
          GitHubとは
        </v-card-title>
        <v-divider></v-divider>
        <div class="reveal">
          <v-card-text class="headline">
            <v-img src="../assets/image_biggest.png"></v-img>
            <p class="text-h2 font-weight-bold text-center">の開発者コミュニティ</p>

            <v-list class="text-h1">
              <v-list-item>4000万人</v-list-item>
              <v-list-item>210万の組織が利用</v-list-item>
            </v-list>
            <!--          <p class="text-h4">世界中のたくさんのプログラムがある！</p>-->
            <p class="text-h4">たとえば…</p>
            <v-container>
              <v-row v-for="example in examplesGitHub" :key="example.name">
                <v-col cols="6" class="text-h2 font-weight-bold pa-0">
                  <a :href="example.pageSource">{{ example.name }}</a>
                  <!--                <v-img :src=example.imgSource-->
                  <!--                       :alt='`GitHubに投稿されている${example.name}のプログラムです。`'-->
                  <!--                       width=auto></v-img>-->
                  <!--                出典：<a>{{ example.pageSource }}</a>-->
                </v-col>
              </v-row>
            </v-container>
          </v-card-text>
        </div>
      </v-col>


      <v-col cols="8">
        <v-card-title class="text-h1 font-weight-bold">
          GitHub Copilotとは
        </v-card-title>
        <v-divider></v-divider>
        <div id=""></div>
        <v-card-text class="headline">
          <v-img src="../assets/image_biggest.png"></v-img>
          <p class="text-h2 font-weight-bold text-center">の開発者コミュニティ</p>

          <v-list class="text-h1">
            <v-list-item>4000万人</v-list-item>
            <v-list-item>210万の組織が利用</v-list-item>
          </v-list>
          <p class="text-h4">世界中のたくさんのプログラムがある！</p>
          たとえば…
            <v-row v-for="example in examplesGitHub" :key="example.name">
              <v-col cols="6">
                <p>{{ example.name }}</p>
                <v-img :src=example.imgSource
                       :alt='`GitHubに投稿されている${example.name}のプログラムです。`'
                       width=auto></v-img>
                出典：<a>{{ example.pageSource }}</a>
              </v-col>
            </v-row>
        </v-card-text>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HowToGitHubCopilot",
  data(){
    return {
      examplesGitHub: [
        {
          "name": "Linux",
          "imgSource": require('../assets/github_linux.png'),
          "pageSource": "https://github.com/torvalds/linux",
        },
        {
          "name": "youtube-dl",
          "imgSource": require('../assets/github_youtubedl.png'),
          "pageSource": "https://github.com/ytdl-org/youtube-dl",
        }
      ],
    }
  },
  methods: {
    reveal: function (){
      const reveals = document.querySelectorAll(".reveal");
      for (let i = 0; i < reveals.length; i++) {
        const windowHeight = window.innerHeight;
        const elTop = reveals[i].getBoundingClientRect().top;
        const elVisible = 150;
        if (elTop < windowHeight - elVisible) {
          reveals[i].classList.add("active");
        } else {
          reveals[i].classList.remove("active");
        }
      }
    },
    EListener: function (){
      const element
      window.addEventListener("click", this.reveal)
    }
  },
  mounted: function(){
    this.EListener()
  }
}
</script>

<style scoped>
.reveal{
  position: relative;
  transform: translateY(150px);
  opacity: 0;
  transition: 2s all ease;
}
.reveal.active{
  transform: translateY(0);
  opacity: 1;
}
</style>