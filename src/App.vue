<template>
  <div >
    <h1>Step:{{page}}</h1>
    <div v-if="page== 1"><HomeScreen></HomeScreen></div>
    <div v-else-if="page== 2"><Inquiry></Inquiry></div>
    <div v-else-if="page== 3"><Questionnaire></Questionnaire></div>
<v-col cols=12 lg=12 md=12 sm=12 align="center">
  <v-btn
    class="btn btn-secondary"
    type="button"
    v-if="page>1"
    @click="page--">前へ戻る</v-btn>
   <v-btn
    class="btn btn-secondary"
    type="button"
    v-if="page<3"
    @click="page++">次へ進む</v-btn>
</v-col>

  </div>
</template>
<script>
import HomeScreen from './components/HomeScreen.vue'
import Inquiry from './components/Inquiry.vue'
import Questionnaire from './components/Questionnaire.vue'


export default {
  name: 'App',
  data: function(){
    return{
      page: 1,
      next: true,
    }
  },
  components: {
  HomeScreen,
  Inquiry,
  Questionnaire
  },
}
</script>


<style>
#app{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
