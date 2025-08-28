<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dynamic Product Filter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
    }
    h2 {
      margin-bottom: 10px;
    }
    select {
      padding: 6px;
      font-size: 16px;
      border-radius: 6px;
      margin-bottom: 20px;
    }
    ul {
      list-style: none;
      padding: 0;
    }
    li {
      padding: 10px;
      margin: 6px 0;
      background: #f0f0f0;
      border-radius: 6px;
    }
  </style>
</head>
<body>
  <h2>Product List</h2>

  <label for="categoryFilter">Filter by Category:</label>
  <select id="categoryFilter">
    <option value="all">All</option>
    <option value="electronics">Electronics</option>
    <option value="clothing">Clothing</option>
    <option value="books">Books</option>
  </select>

  <ul id="productList">
    <li data-category="electronics">Smartphone</li>
    <li data-category="electronics">Laptop</li>
    <li data-category="clothing">T-Shirt</li>
    <li data-category="clothing">Jeans</li>
    <li data-category="books">JavaScript Guide</li>
    <li data-category="books">Data Structures in C++</li>
  </ul>

  <script>
    const filter = document.getElementById("categoryFilter");
    const products = document.querySelectorAll("#productList li");

    filter.addEventListener("change", () => {
      const selected = filter.value;

      products.forEach(product => {
        if (selected === "all" || product.dataset.category === selected) {
          product.style.display = "block";
        } else {
          product.style.display = "none";
        }
      });
    });
  </script>
</body>
</html>
