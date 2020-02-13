<template>
    <h2>{{ translatedText }}</h2>
</template>


<script>
import TranslateForm from '../components/TranslateForm'

export default {
  name: 'translateOut',
    props:
     ['translatedText']
    
}
</script>

<style scoped>

</style>