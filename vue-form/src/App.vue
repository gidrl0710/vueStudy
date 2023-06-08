<template>
  <form v-on:submit.prevent="submitForm"> <!-- event.preventDefault();  -->
    <div>
      <lable for="username">id: </lable>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <lable for="password">pw: </lable>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios'; // npm i axios 설치 필요

export default {
  data: function() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    submitForm: function() {
      //event.preventDefault(); // form 태그의 기본동작 새로고침 막아줌
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(url,data) // 브라우저에서 서버로 데이터를 주고 받기 위한 라이브러리
        .then(function(response){
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
}
</script>

<style>

</style>