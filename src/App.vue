<template>
  <div id="app">
  <h1>World Translator</h1>    
  <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  <TranslateOut v-text="translatedText"></TranslateOut>
  </div>
</template>


<script>
import TranslateForm from './components/TranslateForm'
import TranslateOut from './components/TranslateOut'

export default {
  name: 'app',
  components:{
    TranslateForm,
    TranslateOut
  },
  data(){
    return{
      translatedText:''
    }
  },
  methods:{
   translateText(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200212T152854Z.ee99d1f3c22e96ee.a871a86fe58ce33c0d298b663f3cd4fe744fc9f2&text='+text+'&lang=en-' + language).then((response) => {
        this.translatedText = (response.body.text[0]);
      })
  }


}
}
</script>

<style scoped>

</style>