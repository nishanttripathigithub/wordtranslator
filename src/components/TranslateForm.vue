<template>
  <div id="translateForm">
        <form v-on:submit="formSubmit">
            <input type="text" v-model="textToTranslate" placeholder="Enter text to translate">
            <select v-model="language">
                <option value='ru'>Russian</option>
                <option value='de'>German</option>
                <option value='es'>Spanish</option>
                <option value='fr'>French</option>
            </select>
            <input type="submit" value="Translate">

        </form>
  </div>
</template>


<script>
import TranslateForm from '../components/TranslateForm'

export default {
  name: 'translateForm',
  data(){
      return{
          textToTranslate:'',
          language:''
      }
  },
  created(){
      this.language = 'de'
  },
  methods:{
      formSubmit(e){
        this.$emit('formSubmit',this.textToTranslate, this.language);
        e.preventDefault();
      }
  }
}
</script>

<style scoped>

</style>