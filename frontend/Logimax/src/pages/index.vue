
<script>
  export default {
    data() {
      return {
        message: [],
      };
    },
    mounted() {
      this.fetchMsg();
    },
    methods: {
      async fetchMsg() {
        const response = await fetch("http://127.0.0.1:8000/api/helloworld");
        const data = await response.json();
        this.message = data;
        console.log(data);
      },
      }
    }
</script>

<template>
  <h1>Home</h1>
  <ul>
    <li v-for="msg in message" :key="msg.message">
      {{  msg.message }}
    </li>
  </ul>
</template>
