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

            <v-row justify="center" class="text-h1 text-center">
              <v-col>
                <p class="text-center">4000万人  210万の組織</p>
              </v-col>
            </v-row>
            <!--          <p class="text-h4">世界中のたくさんのプログラムがある！</p>-->
            <v-row>
              <v-col cols="7">
                <p class="text-h4">たとえば…</p>
                <v-container>
                  <v-row v-for="example in examplesGitHub" :key="example.name" class="pb-11">
                    <v-col cols="6" class="text-h2 font-weight-bold pa-0">
                      <a :href="example.pageSource">{{ example.name }}</a>
                    </v-col>
                  </v-row>
                </v-container>
              </v-col>
              <v-col>
                <v-img src="../assets/muryou.png" width="450"></v-img>
              </v-col>
            </v-row>
          </v-card-text>
        </div>
      </v-col>


      <v-col cols="8">
        <v-card-title class="text-h1 font-weight-bold">
          GitHub Copilotとは
        </v-card-title>
        <v-divider></v-divider>
        <div id="" class="reveal">
          <v-card-text class="headline">
            <v-img src="../assets/image_AI.png" width="800" class="mx-auto"></v-img>
            <p class="text-h2 font-weight-bold text-center">によるプログラム自動補完サービス</p>

            <v-row justify="center">
              <v-col>
                <p class="text-center text-h2">学生なら…</p>
              </v-col>
              <v-col>
                <v-img src="../assets/muryou.png" width="450"></v-img>
              </v-col>
            </v-row>

          </v-card-text>
        </div>
      </v-col>


      <v-col cols="8">
        <v-card-title class="text-h1 font-weight-bold">
          GitHub Copilotのしくみ
        </v-card-title>
        <v-divider></v-divider>
<!--        <div id="" class="reveal">-->
        <div>
          <v-card-text class="headline">
            <p class="text-h2 font-weight-bold ">GitHubにある</p>
            <p class="text-h2 font-weight-bold text-center">膨大なプログラムを学習して予測</p>

            <v-img src="../assets/GPT-3_1.png"></v-img>
            <a href="https://www.nri.com/jp/knowledge/glossary/lst/alphabet/gpt_3">
              野村総合研究所 "GPT-3とは"</a>から引用
          </v-card-text>
        </div>
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
      // const elems = document.querySelectorAll(".reveal")
      // for (const elem in elems){
      //   elem.addEventListener("click", this.reveal)
      // }
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