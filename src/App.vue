<template>
  <div class="app">
    <Header title="SoufByQuoter" />
    <div class="bg">
      <Quote :quotes="quotes" />
      <div class="button-block">
        <button @click="getQuotes">Souf Me a Quote</button>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Quote from "./components/Quote.vue";
export default {
  name: "App",
  components: {
    Header,
    Quote,
  },
  data() {
    return {
      quotes: [],
    };
  },
  methods: {
    async getQuotes() {
      const data = await fetch(
        "https://goquotes-api.herokuapp.com/api/v1/random?count=1"
      ).then((res) => res.json());
      this.quotes = {
        text: data.quotes[0].text,
        author: data.quotes[0].author,
        tag: data.quotes[0].tag,
      };
    },
  },
  created() {
    this.getQuotes();
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@300;400;500;700&display=swap");
:root {
  --main-color: #0a043c;
  --second-color: #3e2c41;
  --dark-color: #171717;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: "Oswald", sans-serif;
}
.bg {
  height: calc(100vh - 100px);
  background: linear-gradient(
      rgba(62, 44, 65, 0.9),
      rgba(62, 44, 65, 0.8),
      rgba(62, 44, 65, 0.7),
      rgba(62, 44, 65, 0.6)
    ),
    url("./assets/bg.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
button{
    padding: 15px 30px;
    margin: 30px 0;
    background: var(--second-color);
    color: #fff;
    font-weight: 500;
    font-size: 19px;
    letter-spacing: 1px;
    border: none;
    font-family: "Oswald", sans-serif;
    border-radius: 25px;
    cursor: pointer;
    transition:.3s;
}
button:hover{
    background: var(--dark-color);
}
button:active{
    transform:scale(.98)
}

</style>
