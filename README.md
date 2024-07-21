<style>

    #calculator {
      background-color: #fff;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      padding: 20px;
      border-radius: 8px;
      text-align: center;
      font-color: #30fc03;
      width: 80%;
      max-width: 400px;
        }

    label {
      display: block;
      margin-bottom: 10px;
    }

    select, input {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      box-sizing: border-box;
    }

    button {
      background-color: #4caf50;
      color: #fff;
      padding: 10px;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    #result {
      margin-top: 15px;
    font-weight: bold; 

    }
    #price {
      font-size: 30px;
    }
  </style>
<div id="calculator">
  

  <label style="font-weight: bold; font-size: 22px;" for="unit">Select Unit:</label>
  <select id="unit">
    <option value="gram">Gram</option>
    <option value="tola">Tola</option>
    <option value="Ounce">Ounce</option>
    <option value="Kilo">Kilo</option>


  </select>

  <label style="font-weight: bold; font-size: 22px;" for="karat">Select Purity:</label>
  <select id="karat">
    <option value="24">24k</option>
    <option value="23">23k</option>
    <option value="22">22k</option>
    <option value="21">21k</option>
    <option value="20">20k</option>
    <option value="19">19k</option>
    <option value="18">18k</option>
    <option value="17">17k</option>
    <option value="16">16k</option>
    <option value="15">15k</option>
    <option value="14">14k</option>
    <option value="13">13k</option>
    <option value="12">12k</option>
    <option value="11">11k</option>
    <option value="10">10k</option>
    <option value="9">9k</option>
    <option value="8">8k</option>
    <option value="7">7k</option>
    <option value="6">6k</option>
    <option value="5">5k</option>
    <option value="4">4k</option>
    <option value="3">3k</option>
    <option value="2">2k</option>
    <option value="1">1k</option>
  </select>

  <label style="font-weight: bold; font-size: 22px;" for="weight">Enter Weight:</label>
  <input type="number" id="weight" placeholder="Enter weight" />
  

  <button style="font-size: 20px" onclick="calculatePrice()">Calculate</button>
  <h4 style=" font-color: #30fc03;">Approx Price </h4>

  <div id="result">
    <p id="price"></p>
  </div>
</div>
<script>
  function calculatePrice() {
    const unit = document.getElementById("unit").value;
    const karat = document.getElementById("karat").value;
    const weight = parseFloat(document.getElementById("weight").value);

    // Example pricing structure (replace with your actual pricing information)
    const prices = {
      gram: { 24: 272.47, 23: 261.18 , 22: 249.82 , 21: 238.47 , 20: 227.11 , 19: 215.91 , 18: 204.55 , 17: 193.18  , 16: 181.80  , 15: 170.44 , 14: 159.08 , 13: 147.77  , 12: 136.40 , 11: 125.03 , 10: 113.67 , 9: 102.30  , 8: 90.93  , 7: 79.56   , 6: 68.19  , 5: 56.83  , 4: 45.46 , 3: 34.08 , 2: 22.72 , 1: 11.36 },
      Kilo:{ 24: 272621.06   , 23: 261261.85 , 22: 249902.64 , 21: 238543.42  , 20: 227184.21 , 19: 215915.36 , 18: 204551.39 , 17: 193187.43 , 16: 181823.46 , 15: 170424.73 , 14: 159063.08  , 13: 147701.43 , 12: 136339.79 , 11: 124978.14  , 10: 113616.49  , 9: 102274.19 , 8: 90910.39 , 7: 79546.59  , 6: 68178.53 , 5: 56815.44  , 4: 45452.36  , 3: 34089.27 , 2: 22723.98   , 1: 11361.99  },
      tola: { 24: 3180.58  , 23: 3048.06 , 22: 2915.53  , 21: 2783.94  , 20: 2651.37  , 19: 2518.80  , 18: 2386.23 , 17: 2253.66  , 16: 2120.12  , 15: 1987.61  , 14: 1855.10  , 13: 1722.60  , 12: 1590.09 , 11: 1457.58  , 10: 1326.53  , 9: 1193.88  , 8: 1061.22  , 7: 928.57  , 6: 795.92 , 5: 663.27  , 4: 530.80 , 3: 398.10  , 2: 265.40 , 1: 132.70  },
      Ounce:{24: 8487.36 , 23: 8133.72 , 22: 7780.08  , 21: 7431.59 , 20: 7077.70  , 19: 6723.98 , 18: 6370.08  , 17: 6017.12 , 16: 5663.17 , 15: 5309.22 , 14: 4954.94  , 13: 4601.01  , 12: 4247.09  , 11: 3893.16  , 10: 3184.64  , 9: 2832.58  , 8: 2832.58  , 7: 2478.51   , 6: 2124.64 , 5: 1770.53 , 4: 1416.42  , 3: 1062.32  , 2: 708.24  , 1: 354.12  },


    };

    const price = prices[unit][karat] * weight;

    document.getElementById("price").innerText = `${price.toFixed(2)} QAR`;
  }
</script>
