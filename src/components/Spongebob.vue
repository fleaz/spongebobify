<template>
  <div class="content">
    <input id="input" size=80 v-on:keyup="update" v-model="text">
    <span id="output">{{ output }}</span>
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

#input {
  margin: 50px;
  font-size: 1em;
}

#output {
  margin: 50px;
  width: 100%;
  float: left;
  font-family: Impact;
  font-size: 2.5em;
  color: white;
  text-shadow:2px 2px 0 #000,
  -2px -2px 0 #000,
  2px -2px 0 #000,
  -2px 2px 0 #000,
  0px 2px 0 #000,
  2px 0px 0 #000,
  0px -2px 0 #000,
  -2px 0px 0 #000,
  2px 2px 5px #000;

}
.content:before {
  content: "";
  position: fixed;
  left: 0;
  right: 0;
  z-index: -1;

  display: block;
  background-image: url("/mocking-spongebob.jpg");
  width: 100%;
  height: 100%;

  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  -webkit-filter: blur(5px);
  -moz-filter: blur(5px);
  -o-filter: blur(5px);
  -ms-filter: blur(5px);
  filter: blur(5px);
}
</style>
