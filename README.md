# Temperature-converter-
<div class="container">
  <h1>Temperature Converter</h1>
  <div class="converter-row">
    <div class="col">
      <label>Celsius</label>
      <input type="number" id="celsius">
    </div>
    <div class="col">
      <label>Fahrenheit</label>
      <input type="number" id="fahrenheit">
    </div>
    <div class="col">
      <label>Kelvin</label>
      <input type="number" id="kelvin">
    </div>
  </div>
</div>

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.converter-row {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.col {
  display: flex;
  flex-direction: column;
  margin: 0 10px;
}

input[type="number"] {
  width: 100px;
  padding: 5px;
  margin-top: 5px;
  border-radius: 5px;
  border: none;
  text-align: center;
}
let celsius = document.getElementById('celsius');
let fahrenheit = document.getElementById('fahrenheit');
let kelvin = document.getElementById('kelvin');

celsius.oninput = function () {
  let f = (parseFloat(celsius.value) * 9) / 5 + 32;
  fahrenheit.value = parseFloat(f.toFixed(2));
  let k = parseFloat(celsius.value) + 273.15;
  kelvin.value = parseFloat(k.toFixed(2));
};

fahrenheit.oninput = function () {
  let c = ((parseFloat(fahrenheit.value) - 32) * 5) / 9;
  celsius.value = parseFloat(c.toFixed(2));
  let k = ((parseFloat(fahrenheit.value) - 32) * 5) / 9 + 273.15;
  kelvin.value = parseFloat(k.toFixed(2));
};

kelvin.oninput = function () {
  let c = parseFloat(kelvin.value) - 273.15;
  celsius.value = parseFloat(c.toFixed(2));
  let f = ((parseFloat(kelvin.value) - 273.15) * 9) / 5 + 32;
  fahrenheit.value = parseFloat(f.toFixed(2));
};
