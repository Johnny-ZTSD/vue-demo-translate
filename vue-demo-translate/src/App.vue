<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <hello></hello> -->
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单 / 易用 / 便捷</h5>
    <TranslateForm v-on:formSubmitEvent="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
    <h6>From Johnny Zen</h6>
<!--     <h4 v-text="test01"></h4>
    <input type="text" v-text="test01">
    <input type="text" v-model="test01"> -->
  </div>
</template>

<script>
import Hello from './components/Hello'
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    Hello, 
    TranslateForm,
    TranslateOutput
  },
  data:function(){
    return{
      translatedText:"",
      // test01:"12123456"
    }
  },
  methods:{
    translateText:function(text,language){
      //需要引入vueResource包【http等】
      //npm install vue-resource --save   
      // alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170829T154423Z.0b14a4fc0554ab4c.239cc168ff03697822888fc1013796128640599f&lang=' + language + '&text=' + text).then((response)=>{
        // console.log(response.body.text[0]);
        this.translatedText = response.body.text[0];
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
