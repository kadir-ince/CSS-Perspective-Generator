<script>
export default {
  data() {
    return {
      perspective: 100,
      rotateX: 0,
      rotateY: 0,
      rotateZ: 0,
    };
  },
  computed: {
    box() {
      return {
        transform: `
        perspective(${this.perspective}px)
        rotateX(${this.rotateX}deg)
        rotateY(${this.rotateY}deg)
        rotateZ(${this.rotateZ}deg)
        `,
      };
    },
  },
  methods: {
    reset() {
      this.perspective = 100;
      this.rotateX = 0;
      this.rotateY = 0;
      this.rotateZ = 0;
    },
    copy() {
      const codeText = document.createElement("textarea");
      codeText.value = `transform: ${this.box.transform}`;

      document.body.appendChild(codeText);
      codeText.select();

      document.execCommand("copy");
      document.body.removeChild(codeText);
    },
  },
};
</script>

<template>
  <div>
    <h2>CSS3 Perspective Playground</h2>
    <main>
      <section class="settings">
        <div class="settings-container">
          <label>perspective: {{ perspective }}px;</label>
          <input type="range" min="0" max="999" v-model="perspective" />

          <label>rotateX: {{ rotateX }}deg; </label>
          <input type="range" min="-180" max="180" v-model="rotateX" />

          <label>rotateY: {{ rotateY }}deg; </label>
          <input type="range" min="-180" max="180" v-model="rotateY" />

          <label>rotateZ: {{ rotateZ }}deg; </label>
          <input type="range" min="-180" max="180" v-model="rotateZ" />

          <button type="button" @click.prevent="reset">Reset</button>
          <button type="button" @click.prevent="copy" class="button">
            Copy Code
          </button>
        </div>
      </section>
      <section class="output">
        <div class="box-container">
          <div class="box" v-bind:style="box"></div>
        </div>
      </section>
    </main>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Raleway:wght@500&display=swap");
html {
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}

*,
*:before,
*:after {
  box-sizing: inherit;
  padding: 0;
  margin: 0;
}
body {
  font-family: sans-serif;
  height: 100%;
  margin: 0;
  background: #261c33;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

h2 {
  color: #8d81f3;
  text-align: center;
  font-size: 40px;
  margin: 20px;
  color: #8d81f3;
}
main {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 420px;
  max-width: 768px;
  margin: 0 auto;
  font-family: monospace, sans-serif;
  font-size: 22px;
}
main label {
  display: block;
}
main input[type="range"] {
  display: block;
  margin-bottom: 10px;
  width: 200px;
}
section.settings {
  width: 50%;
  z-index: 2;
}
.box-container {
  padding: 50px;
  border: 2px solid #8d81f3;
  border-radius: 12px;
  box-shadow: 5px 5px 45px 0px rgba(255, 255, 255, 0.8);
}
.box {
  width: 150px;
  height: 150px;
  background: #8d81f3;
}

button {
  background-color: #594fec;
  color: #fff;
  display: inline-block;
  font-size: 20px;
  padding: 10px;
  outline: none;
  border: none;
  border-radius: 8px;
  font-family: "Raleway", sans-serif;
  margin-right: 10px;
  cursor: pointer;
}

label {
  color: #fff;
}
</style>
