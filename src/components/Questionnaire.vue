
<template>
  <v-container>
    <v-row class="flex-column" >
      <v-card class="mx-auto" width="900" max-width="900">
        <v-col cols="12" class="blue lighten-4">以下にお答えください</v-col>
          <v-card-text>
            <div class="mb-4" v-show="currentQuestion >= 1">
              <p>現在、生命保険に加入されていますか？</p>
              <v-col cols="12" sm="6" md="6">
                <v-radio-group column :items ="answer1" v-model="answer1">
                  <v-radio label="はい" color="secondary" value="yes" @click="nextButton()"></v-radio>
                  <v-radio label="いいえ" color="secondary" value="no" @click="nextButton()"></v-radio>
                </v-radio-group>
              </v-col>
            </div>
            <div class="mb-4" v-show="currentQuestion >= 2">
              <p>現在入院中ですか。または、最近3ヶ月以内に医師の診断・検査の結果、入院・手術をすすめられたことはありますか？</p>
              <v-col cols="12" sm="6" md="6">
                <v-radio-group column :items ="answer2" v-model="answer2">
                  <v-radio label="はい" color="secondary" value="yes" @click="nextButton()"></v-radio>
                  <v-radio label="いいえ" color="secondary" value="no" @click="nextButton()"></v-radio>
                </v-radio-group>
              </v-col>
            </div>
              <div class="mb-4" v-show="currentQuestion >= 3">
                <p>過去５年間に、病気やけがで、手術を受けた事または継続して7日以上の入院をしたことがありますか？</p>
                <v-col cols="12" sm="6" md="6">
                <v-radio-group column :items ="answer3" v-model="answer3">
                  <v-radio label="はい" color="secondary" value="yes" @click="nextButton()"></v-radio>
                  <v-radio label="いいえ" color="secondary" value="no" @click="nextButton()"></v-radio>
                </v-radio-group>
              </v-col>
              </div>
          </v-card-text>
        </v-card>
    </v-row>
  </v-container>
</template>

<script>
  export default {
  data: () => ({
    currentQuestion:1,
    answer1: '',
    answer2: '',
    answer3: '',
  }),
  methods:{
     nextButton:function(){ this.currentQuestion++; if (this.currentQuestion > 3) { this.currentQuestion = 3; } },
     backButton:function(){ this.currentQuestion--; if (this.currentQuestion < 1) { this.currentQuestion = 1; } },
   },
  computed: {

  },

}
</script>
