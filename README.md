<html>
<head>
  <title>Shirt Order Form</title>
  <style>
    body { font-family: Arial; margin: 20px; }
    form { max-width: 500px; margin: auto; }
    label { display: block; margin-top: 10px; }
    input, select { width: 100%; padding: 8px; margin-top: 5px; }
    button { margin-top: 15px; padding: 10px; background: #4CAF50; color: white; border: none; cursor: pointer; }
    button:hover { background: #45a049; }
  </style>
</head>
<body>
  <h2>Shirt Order Form</h2>
  <form id="orderForm">
    <label>Name:</label>
    <input type="text" name="name" required>

    <label>Type of Shirt:</label>
    <select name="shirtType" required>
      <option value="Short Sleeve">Short Sleeve</option>
      <option value="Long Sleeve">Long Sleeve</option>
      <option value="Crew Neck">Crew Neck</option>
      <option value="Hoodie">Hoodie</option>
    </select>

    <label>Child Medium:</label>
    <input type="number" name="childMedium" min="0">

    <label>Child Large:</label>
    <input type="number" name="childLarge" min="0">

    <label>Adult S:</label>
    <input type="number" name="adultS" min="0">

    <label>Adult M:</label>
    <input type="number" name="adultM" min="0">

    <label>Adult L:</label>
    <input type="number" name="adultL" min="0">

    <label>Adult XL:</label>
    <input type="number" name="adultXL" min="0">

    <label>Adult 2X:</label>
    <input type="number" name="adult2X" min="0">

    <label>Adult 3X:</label>
    <input type="number" name="adult3X" min="0">

    <button type="submit">Submit</button>
  </form>

  <script>
    const scriptURL = "YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL";
    document.getElementById("orderForm").addEventListener("submit", e => {
      e.preventDefault();
      const formData = new FormData(e.target);
      const data = Object.fromEntries(formData.entries());
      fetch(scriptURL, {
        method: "POST",
        body: JSON.stringify(data)
      }).then(response => alert("Order submitted successfully!"))
        .catch(error => alert("Error: " + error));
    });
  </script>
</body>
</html>
