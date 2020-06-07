<template>
  <div>
      <div class="bg-image"></div>
      <div class="content">
        <p id="output">{{ output }}</p>
        <input id="input" placeholder="Write something..." v-on:keyup="update" v-model="text">
      </div>
  </div>
</template>

<script>
export default {
  name: "Spongebob",
  data: function() {
    return {
      text: "",
      output: ""
    };
  },
  methods: {
    update: function() {
      this.output = this.alternatingCase(this.text);
    },
    alternatingCase: function(input) {
      let output = ""
      let caps = true 
      input.split('').forEach(element => {
        if (caps) {
          output +=  element.toUpperCase();
        } else {
          output +=  element.toLowerCase();
        }
        caps = !caps;
      });

      return output
    }
  }
};
</script>

<style scoped>

.content {
    font-size: 2rem;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
    text-align: center;
}
 .content input {
    padding: 10px;
    max-width:80%;
    font-size: 2rem;
}

.content > p {
    font-size: 3rem;
    font-weight: bold;
    font-family: Impact, Charcoal, sans-serif;
    color: white;
      -webkit-text-stroke: 2px black;
}

.bg-image {
    height: 100vh;
    background-image: url("/mocking-spongebob.jpg");
    background-repeat: no-repeat;
    background-size: 100% 100%;
    filter: blur(8px);
    -webkit-filter: blur(8px);
}
</style>
