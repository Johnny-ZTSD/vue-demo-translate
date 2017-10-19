<template>
  <div class="row" id="translateForm">
    <!-- translateForm -->
      <div class="col-md-6 col-md-offset-3">
          <form id="transForm" class="well form-inline" v-on:submit="formSubmit">
          <input class="form-control" type="text" name="" v-model="textToTranslate">
          <select class="form-control"  v-model="language">
            <option value="en">English</option>
            <option value="ch">中文</option>
            <option value="ru">Русский</option>
            <option value="ja">日本語</option>
          </select>
          <input class="btn btn-primary" type="submit" value="Translate">
        </form>
      </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data() {
    return {
      textToTranslate:"",
      language:"en"
    }
  },
  methods:{
    // check:function(){
    //   if(this.textToTranslate.length < 1)
    //       return false;
    //   else
    //       return true;
    // },
    formSubmit:function(e){
      // if(check() != true)
      //     return; 
      // // alert(this.textToTranslate);
      this.$emit("formSubmitEvent",this.textToTranslate,this.language);//注册(回调)事件【参数：需要注册的事件(自定义事件名)】
      e.preventDefault();//阻止默认事件
    }
  }
}
</script>

<style>
  #transForm{
    border-radius: 10px;
    border:1px solid #ccc;
    
  }
</style>
