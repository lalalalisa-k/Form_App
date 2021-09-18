<template>
  <v-container>
    <v-row class="flex-column">
      <v-card class="mx-auto" width="900" max-width="900">
        <v-col cols="12" class="blue lighten-4">お客様の情報を入力してください</v-col>
          <v-card-text>
            <div class="mb-4">- 性別 -</div>
              <v-col cols="12" sm="6" md="6">
                <v-radio-group column :items ="gender" v-model="gender">
                  <v-radio label="男性" color="secondary" value="male"></v-radio>
                  <v-radio label="女性" color="secondary" value="female"></v-radio>
                </v-radio-group>
              </v-col>
            <div class="mb-4">- 生年月日 -</div>
              <v-row>
                <v-col cols="6">
              <v-select label="西暦" :items="years" v-model="year" @change="resetDay" filled dense></v-select>
            </v-col>
            <v-col cols="3">
              <v-select label="月" :items="months" v-model="month" @change="resetDay" filled dense></v-select>
            </v-col>
            <v-col cols="3">
              <v-select label="日" :items="days" v-model="day" filled dense></v-select>
            </v-col>
              </v-row>
          </v-card-text>
        </v-card>

    </v-row>
  </v-container>
</template>



<script>


  export default {
  data: () => ({
    year: '',
    month: '',
    day: '',
    gender: '',
  }),
  methods: {
    resetDay() {
      this.day = ''
    },
  },
  theme: {
    themes: {
      light: {
        primary: '#3f51b5',
        secondary: '#b0bec5',
        accent: '#8c9eff',
        error: '#b71c1c',
      },
    },
  },
  computed: {
    years() {
      const years = []
      for (let year = 1900; year <= new Date().getFullYear(); year++) {
        years.push(year)
      }
      return years
    },
    months() {
      const months = [...Array(12)].map((ele, i) => i + 1)
      return months
    },
    days() {
      let days = []
      if ((this.month === 2 && this.year % 4 === 0 && this.year % 100 !== 0) || (this.month === 2 && this.year % 400 === 0)) {
        days = [...Array(29)].map((ele, i) => i + 1)
      } else if (this.month === 2) {
        days = [...Array(28)].map((ele, i) => i + 1)
      } else if (this.month === 4 || this.month === 6 || this.month === 9 || this.month === 11) {
        days = [...Array(30)].map((ele, i) => i + 1)
      } else {
        days = [...Array(31)].map((ele, i) => i + 1)
      }
      return days
    },
  },
//router
}
</script>
