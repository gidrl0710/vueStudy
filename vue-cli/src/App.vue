<template> 
  <div id="app"> <!-- ROOT element 는 무조건하나!! -->
    <!-- <app-header v-bind:프롭스 속성 이름="상위 컴포넌트의 데이터 이름"></app-header> -->
        <header-app v-bind:propsdata="str" v-on:renew="renewStr"></header-app>
  </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue';
// new Vue({
//   data: {
//     str: 'hello'
//   }
// })

export default { 
  // 데이터는 함수안에 return으로 사용 
  data: function() {
    return {
      str: 'Header'
    }
  },
  components: {
    'header-app': HeaderApp
  },
  methods: {
    renewStr: function() {
      this.str='Header Changed';
    }
  }
}
</script>

<style>

</style>