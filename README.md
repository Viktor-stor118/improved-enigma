<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <title id="shop-title">Мій Магазин</title>
  <style>
    body { font-family: Arial, sans-serif; background: #fafafa; margin: 0; padding: 0; }
    header { background: #0074d9; color: #fff; padding: 20px; text-align: center; }
    #edit-title { background: #fff; color: #0074d9; border: none; padding: 2px 6px; cursor: pointer; margin-left: 10px; }
    main { display: flex; justify-content: space-around; align-items: flex-start; padding: 30px 0; flex-wrap: wrap; }
    section { background: #fff; padding: 15px 25px; border-radius: 8px; box-shadow: 0 2px 6px #ccc; width: 340px; margin-bottom: 30px;}
    h2 { margin-top: 0; }
    .product-list { list-style: none; padding: 0; }
    .product-list li { border-bottom: 1px solid #eee; margin-bottom: 8px; padding-bottom: 6px; }
    .product-list li:last-child { border: none; }
    label { display: block; margin-top: 10px; margin-bottom: 4px; }
    input, textarea { width: 100%; padding: 7px; border-radius: 4px; border: 1px solid #bbb; }
    button { margin-top: 10px; background: #0074d9; color: #fff; border: none; padding: 7px 16px; border-radius: 4px; cursor: pointer; }
    button:hover { background: #005fa3; }
    .contact-success { color: green; margin-top: 10px; }
    @media (max-width: 800px) {
      main { flex-direction: column; align-items: center; }
      section { width: 90%; }
    }
  </style>
</head>
<body>
  <header>
    <span id="shopName">Мій Магазин</span>
    <button id="edit-title">Змінити назву</button>
  </header>
  <main>
    <section>
      <h2>Додати товар</h2>
      <form id="product-form">
        <label>Назва товару:</label>
        <input type="text" id="product-name" required>
        <label>Ціна (грн):</label>
        <input type="number" id="product-price" required min="1">
        <button type="submit">Додати</button>
      </form>
      <h2>Товари</h2>
      <ul id="product-list" class="product-list"></ul>
    </section>
    <section>
      <h2>Зв’язатися з нами</h2>
      <form id="contact-form">
        <label>Ваше ім’я:</label>
        <input type="text" id="client-name" required>
        <label>Ваш email:</label>
        <input type="email" id="client-email" required>
        <label>Повідомлення:</label>
        <textarea id="client-message" required></textarea>
        <button type="submit">Відправити</button>
      </form>
      <div id="contact-success" class="contact-success"></div>
    </section>
  </main>
  <script>
    // Зміна назви магазину
    document.getElementById('edit-title').onclick = function() {
      const newName = prompt("Введіть нову назву магазину:", document.getElementById('shopName').textContent);
      if (newName && newName.trim()) {
        document.getElementById('shopName').textContent = newName;
        document.title = newName;
      }
    };

    // Додавання товару
    document.getElementById('product-form').onsubmit = function(e) {
      e.preventDefault();
      const name = document.getElementById('product-name').value.trim();
      const price = document.getElementById('product-price').value;
      if (name && price) {
        const li = document.createElement('li');
        li.textContent = name + ' — ' + price + ' грн';
        document.getElementById('product-list').appendChild(li);
        this.reset();
      }
    };

    // Зв'язок з клієнтом (імітація)
    document.getElementById('contact-form').onsubmit = function(e) {
      e.preventDefault();
      // В реальному магазині тут має бути відправка на сервер!
      document.getElementById('contact-success').textContent =
        "Дякуємо, ваше повідомлення надіслано!";
      this.reset();
      setTimeout(() => document.getElementById('contact-success').textContent = '', 3500);
    };
  </script>
</body>
</html><!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <title id="shop-title">Мій Магазин</title>
  <style>
    body { font-family: Arial, sans-serif; background: #fafafa; margin: 0; padding: 0; }
    header { background: #0074d9; color: #fff; padding: 20px; text-align: center; }
    #edit-title { background: #fff; color: #0074d9; border: none; padding: 2px 6px; cursor: pointer; margin-left: 10px; }
    main { display: flex; justify-content: space-around; align-items: flex-start; padding: 30px 0; flex-wrap: wrap; }
    section { background: #fff; padding: 15px 25px; border-radius: 8px; box-shadow: 0 2px 6px #ccc; width: 340px; margin-bottom: 30px;}
    h2 { margin-top: 0; }
    .product-list { list-style: none; padding: 0; }
    .product-list li { border-bottom: 1px solid #eee; margin-bottom: 8px; padding-bottom: 6px; }
    .product-list li:last-child { border: none; }
    label { display: block; margin-top: 10px; margin-bottom: 4px; }
    input, textarea { width: 100%; padding: 7px; border-radius: 4px; border: 1px solid #bbb; }
    button { margin-top: 10px; background: #0074d9; color: #fff; border: none; padding: 7px 16px; border-radius: 4px; cursor: pointer; }
    button:hover { background: #005fa3; }
    .contact-success { color: green; margin-top: 10px; }
    @media (max-width: 800px) {
      main { flex-direction: column; align-items: center; }
      section { width: 90%; }
    }
  </style>
</head>
<body>
  <header>
    <span id="shopName">Мій Магазин</span>
    <button id="edit-title">Змінити назву</button>
  </header>
  <main>
    <section>
      <h2>Додати товар</h2>
      <form id="product-form">
        <label>Назва товару:</label>
        <input type="text" id="product-name" required>
        <label>Ціна (грн):</label>
        <input type="number" id="product-price" required min="1">
        <button type="submit">Додати</button>
      </form>
      <h2>Товари</h2>
      <ul id="product-list" class="product-list"></ul>
    </section>
    <section>
      <h2>Зв’язатися з нами</h2>
      <form id="contact-form">
        <label>Ваше ім’я:</label>
        <input type="text" id="client-name" required>
        <label>Ваш email:</label>
        <input type="email" id="client-email" required>
        <label>Повідомлення:</label>
        <textarea id="client-message" required></textarea>
        <button type="submit">Відправити</button>
      </form>
      <div id="contact-success" class="contact-success"></div>
    </section>
  </main>
  <script>
    // Зміна назви магазину
    document.getElementById('edit-title').onclick = function() {
      const newName = prompt("Введіть нову назву магазину:", document.getElementById('shopName').textContent);
      if (newName && newName.trim()) {
        document.getElementById('shopName').textContent = newName;
        document.title = newName;
      }
    };

    // Додавання товару
    document.getElementById('product-form').onsubmit = function(e) {
      e.preventDefault();
      const name = document.getElementById('product-name').value.trim();
      const price = document.getElementById('product-price').value;
      if (name && price) {
        const li = document.createElement('li');
        li.textContent = name + ' — ' + price + ' грн';
        document.getElementById('product-list').appendChild(li);
        this.reset();
      }
    };

    // Зв'язок з клієнтом (імітація)
    document.getElementById('contact-form').onsubmit = function(e) {
      e.preventDefault();
      // В реальному магазині тут має бути відправка на сервер!
      document.getElementById('contact-success').textContent =
        "Дякуємо, ваше повідомлення надіслано!";
      this.reset();
      setTimeout(() => document.getElementById('contact-success').textContent = '', 3500);
    };
  </script>
</body>
</html>

