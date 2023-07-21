<script setup>
import axios from "axios";

let number = ''

const send = () => {
  axios({
    url: 'http://127.0.0.1:52273/',
    method: 'POST',
    data: {
      number: this.number,
    }
  }).then((res) => {
    alert(res.data.message)
  })
}
</script>

<template>
  <div id="app">
    <v-form ref="form" @submit.prevent="send">
      <v-text-field v-model="number" label="숫자를 입력하세요." :style="{width: '200px'}"/>
      <v-btn type="submit">전송</v-btn>
    </v-form>
  </div>
</template>

<style scoped>
</style>
