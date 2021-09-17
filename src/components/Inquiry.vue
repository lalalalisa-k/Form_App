
<template>
  <v-container>
    <v-row class="flex-column" >
      <v-card  width="900">
        <v-col cols="12" class="blue lighten-4">ご相談内容をご記入ください</v-col>
          <div class="mb-4">- ご相談内容 -</div>
            <v-col>
              <v-textarea
          solo
          name="input-7-4"
          label="Solo textarea" :items ="answer" v-model="answer"
        ></v-textarea>
            </v-col>
          <v-card-text>
          </v-card-text>
        </v-card>
    </v-row>
  </v-container>
</template>

<script>
  export default {
  data: () => ({
    answer: '',

  }),
  methods: {

    },
  computed: {

  },

}
</script>
