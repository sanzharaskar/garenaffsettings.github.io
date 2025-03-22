<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Free Fire Настройки Samsung</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Arial', sans-serif;
      background-image: url('https://i.imgur.com/yX1tV1R.jpg'); /* Фон как в игре */
      background-size: cover;
      background-position: center;
      color: #fff;
      text-shadow: 1px 1px 2px black;
    }

    .container {
      max-width: 700px;
      margin: 60px auto;
      background-color: rgba(0, 0, 0, 0.7);
      padding: 30px;
      border-radius: 12px;
    }

    h1 {
      text-align: center;
      font-size: 26px;
      margin-bottom: 20px;
    }

    label, select {
      display: block;
      margin: 15px 0 5px;
      font-size: 18px;
    }

    .settings-box {
      margin-top: 20px;
      padding: 20px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
    }

    .setting {
      margin-bottom: 12px;
      font-size: 16px;
    }

    select, button {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border-radius: 8px;
      border: none;
    }

    button {
      background-color: #ffcc00;
      color: #000;
      font-weight: bold;
      cursor: pointer;
      margin-top: 20px;
    }

    button:hover {
      background-color: #ffaa00;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Настройки чувствительности Free Fire (Samsung)</h1>

    <label for="model">Выберите модель Samsung:</label>
    <select id="model">
      <option value="">-- Выбрать --</option>
      <!-- Серии A -->
      <option value="A01">Samsung A01</option>
      <option value="A02">Samsung A02</option>
      <option value="A03">Samsung A03</option>
      <option value="A10">Samsung A10</option>
      <option value="A11">Samsung A11</option>
      <option value="A12">Samsung A12</option>
      <option value="A13">Samsung A13</option>
      <option value="A20">Samsung A20</option>
      <option value="A21">Samsung A21</option>
      <option value="A22">Samsung A22</option>
      <option value="A23">Samsung A23</option>
      <option value="A30">Samsung A30</option>
      <option value="A31">Samsung A31</option>
      <option value="A32">Samsung A32</option>
      <option value="A33">Samsung A33</option>
      <option value="A50">Samsung A50</option>
      <option value="A51">Samsung A51</option>
      <option value="A52">Samsung A52</option>
      <option value="A53">Samsung A53</option>
      <option value="A70">Samsung A70</option>
      <option value="A71">Samsung A71</option>
      <option value="A72">Samsung A72</option>
      <!-- Серия S -->
      <option value="S8">Samsung S8</option>
      <option value="S9">Samsung S9</option>
      <option value="S10">Samsung S10</option>
      <option value="S20">Samsung S20</option>
      <option value="S21">Samsung S21</option>
      <option value="S22">Samsung S22</option>
      <option value="S23">Samsung S23</option>
      <option value="S24">Samsung S24</option>
    </select>

    <button onclick="showSettings()">Показать настройки</button>

    <div class="settings-box" id="result" style="display: none;"></div>
  </div>

  <script>
    const settings = {
      A01: [90, 80, 85, 70, 85, 60],
      A02: [95, 85, 90, 75, 80, 62],
      A03: [100, 88, 93, 78, 82, 63],
      A10: [98, 84, 88, 74, 81, 61],
      A11: [97, 83, 87, 72, 80, 60],
      A12: [96, 85, 89, 73, 83, 62],
      A13: [94, 86, 90, 76, 84, 63],
      A20: [91, 82, 86, 70, 78, 59],
      A21: [90, 83, 85, 72, 79, 58],
      A22: [89, 84, 86, 73, 80, 60],
      A23: [88, 85, 87, 74, 81, 62],
      A30: [100, 95, 98, 85, 90, 70],
      A31: [102, 94, 97, 84, 91, 72],
      A32: [104, 96, 99, 86, 92, 73],
      A33: [105, 97, 100, 87, 93, 75],
      A50: [110, 100, 105, 90, 95, 78],
      A51: [112, 102, 107, 91, 97, 79],
      A52: [115, 104, 110, 93, 98, 80],
      A53: [117, 105, 112, 94, 99, 82],
      A70: [120, 108, 115, 95, 100, 85],
      A71: [122, 110, 117, 96, 101, 86],
      A72: [125, 112, 119, 97, 102, 88],
      S8: [130, 115, 120, 98, 105, 90],
      S9: [132, 116, 122, 99, 106, 91],
      S10: [135, 118, 125, 100, 108, 92],
      S20: [140, 120, 128, 103, 110, 95],
      S21: [145, 125, 130, 105, 112, 97],
      S22: [150, 130, 135, 108, 115, 100],
      S23: [155, 135, 140, 110, 118, 105],
      S24: [160, 140, 145, 112, 120, 108]
    };

    function showSettings() {
      const model = document.getElementById('model').value;
      const resultBox = document.getElementById('result');

      if (!settings[model]) {
        resultBox.style.display = 'block';
        resultBox.innerHTML = 'Выберите модель телефона.';
        return;
      }

      const [general, x2, x4, sniper, freeLook, fireBtn] = settings[model];

      resultBox.style.display = 'block';
      resultBox.innerHTML = `
        <div class="setting">Обычная стрельба: <strong>${general}</strong></div>
        <div class="setting">2x прицел: <strong>${x2}</strong></div>
        <div class="setting">4x прицел: <strong>${x4}</strong></div>
        <div class="setting">Снайперская чувствительность: <strong>${sniper}</strong></div>
        <div class="setting">Свободный обзор: <strong>${freeLook}</strong></div>
        <div class="setting">Размер кнопки огня: <strong>${fireBtn}</strong></div>
      `;
    }
  </script>
</body>
</html>
