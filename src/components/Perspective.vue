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
};
</script>

<template>
  <div>
    <h2>CSS3 Perspective Playground</h2>
    <main>
      <section class="settings">
        <div class="settings-container">
          <label>perspective: 0px;</label>
          <input type="range" min="0" max="999" />

          <label>rotateX: 0deg; </label>
          <input type="range" min="-180" max="180" />

          <label>rotateY: 0deg; </label>
          <input type="range" min="-180" max="180" />

          <label>rotateZ: 0deg; </label>
          <input type="range" min="-180" max="180" />

          <button type="button">Reset</button>
          <button type="button">Copy</button>
        </div>
      </section>
      <section class="output">
        <div class="box-container">
          <div class="box"></div>
        </div>
      </section>
    </main>
  </div>
</template>

<style>
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
  border: 1px solid #8d81f3;
}
.box {
  width: 150px;
  height: 150px;
  background: #8d81f3;
}

button {
  background-color: #8d81f3;
  color: #fff;
  display: inline-block;
  font-size: 20px;
  padding: 10px;
  outline: none;
  border: none;
  margin-right: 10px;
}

label {
  color: #fff;
}
</style>
