<script>
export default {
  methods: {
    calc: function(operation) {
      const num1 = parseFloat(document.getElementById('input-num1').value);
      const num2 = parseFloat(document.getElementById('input-num2').value);
      let result;

      switch (operation) {
        case '+':
          result = num1 + num2;
          break;
        case '-':
          result = num1 - num2;
          break;
        case '*':
          result = num1 * num2;
          break;
        case '/':
          result = num1 / num2;
          break;
        default:
          result = 'Error';
      }
      document.getElementById("answer").placeholder = result;
    }
  }
}
</script>

<template>
  <div class="wrapper-full">
    <div class="wrapper">
      <div class="content">

        <input type="number" id="input-num1" placeholder="27">
        <input type="number" id="input-num2" placeholder="4"> <span style="color: white;">=</span>
        <input type="number" id="answer" placeholder="" disabled>
        <br>

        <div class="buttons">
          <button class="calc-btn" v-on:click="calc('+')">+</button>
          <button class="calc-btn" v-on:click="calc('-')">−</button>
          <button class="calc-btn" v-on:click="calc('*')">×</button>
          <button class="calc-btn" v-on:click="calc('/')">÷</button>
        </div>

      </div>
    </div>
  </div>
</template>

<style>

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

.wrapper-full{
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh;
  width: 70vw;

  background-color: #2c3e50;
  border-radius: 12px;
  padding: 20px;
}
#input-num1, #input-num2, #answer {
  width: 200px;
  height: 50px;
  font-size: 20px;
  text-align: center;

  border: 0;
  border-radius: 5px;

  background-color: #B2B2B2;

  margin: 10PX;
}
#answer::placeholder {
  color: #000
}
.calc-btn {
  margin: 10px;
  height: 45px;
  width: 60px;
  font-size: 40px;

  border: 0;
  border-radius: 5px;

  background-color: #00ABB3;
  transition: background-color 0.5s ease;

  color: white;

}
.calc-btn:hover {
  cursor: pointer;
  background-color: #fac99e;
}
.buttons {
  display: flex;
  justify-content: center;
}

</style>