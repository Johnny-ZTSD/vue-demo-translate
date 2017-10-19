<template>
  <div id="TranslateOutput">
    <!-- TranslateOutput -->
    <p>
    	{{ translatedText }}<!-- 使用属性 -->
    </p>
  </div>
</template>

<script>
export default {
  name: 'TranslateOutput',
  props:{//注册属性
  	"translatedText":""
  }
}
</script>

<style>
</style>
