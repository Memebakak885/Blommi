
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bloomi</title>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Open+Sans&display=swap">
  <style>
    /* Reset de margenes y padding */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    
    /* Fondo y colores generales */
    body {
      font-family: 'Open Sans', sans-serif;
      background-color: #fef9f2;  /* Fondo beige muy suave */
      color: #2e2e2e;  /* Letras más oscuras para mayor contraste */
      line-height: 1.6;
    }
    
    header {
      background-color: #f0c8e1;  /* Rosa pastel suave */
      color: #fff;
      padding: 3rem 2rem;
      text-align: center;
      border-bottom: 2px solid #d8a0b6;
    }

    header h1 {
      font-size: 3rem;
      font-family: 'Playfair Display', serif;
    }

    header p {
      font-size: 1.2rem;
    }

    /* Estilos del menú de navegación */
    nav {
      display: flex;
      justify-content: center;
      gap: 2rem;
      background-color: #d0b6ff;  /* Lila bebé */
      padding: 1rem;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      text-transform: uppercase;
    }

    nav a:hover {
      color: #f8e9f1;
      text-decoration: underline;
    }

    /* Estilo de las secciones */
    .section {
      padding: 4rem 2rem;
      max-width: 1200px;
      margin: auto;
      text-align: center;
    }

    .section h2 {
      font-family: 'Playfair Display', serif;
      margin-bottom: 1rem;
      color: #f0c8e1;
      font-size: 2rem;
    }

    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
      justify-items: center;
      margin-top: 2rem;
    }

    .product {
      background: white;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      padding: 1rem;
      text-align: center;
      transition: transform 0.3s ease-in-out;
    }

    .product:hover {
      transform: translateY(-10px);  /* Animación de elevación */
    }

    .product img {
      width: 100%;
      border-radius: 10px;
      margin-bottom: 1rem;
    }

    .product h3 {
      color: #f0c8e1;
      margin-bottom: 0.5rem;
    }

    .product p {
      font-size: 1rem;
      color: #333;
    }

    .product button {
      background-color: #d0b6ff;  /* Lila bebé */
      border: none;
      padding: 0.8rem 1.2rem;
      margin-top: 1rem;
      color: white;
      font-weight: bold;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    .product button:hover {
      background-color: #a79eff;  /* Lila más claro */
      color: #333;
    }

    #cart {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background: #d70080;  /* Fucsia */
      color: white;
      padding: 1.5rem;
      border-radius: 8px;
      max-width: 300px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      z-index: 1000;
    }

    #checkout-btn {
      background-color: #f18fbf;  /* Rosa fuerte para finalizar compra */
      color: white;
      font-weight: bold;
      border: none;
      padding: 1rem 2rem;
      border-radius: 5px;
      cursor: pointer;
      margin-top: 1rem;
      transition: background-color 0.3s;
    }

    #checkout-btn:hover {
      background-color: #f8b8c7;  /* Rosa más claro */
      color: #333;
    }

    footer {
      background: #2B2B2B;
      color: #FAF4ED;
      text-align: center;
      padding: 2rem;
      margin-top: 2rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Bloomi</h1>
    <p>El regalo que no se marchita</p>
  </header>

  <nav>
    <a href="#nosotros">Nosotros</a>
    <a href="#precios">Precios</a>
    <a href="#entrega">Lugares de entrega</a>
    <a href="#contacto">Contacto</a>
  </nav>

  <section class="section" id="nosotros">
    <h2>Nosotros</h2>
    <p>Somos Bloomi, una tienda especializada en flores eternas preservadas con amor y dedicación. Nuestro objetivo es ofrecer un regalo elegante que perdure en el tiempo y transmita emociones reales.</p>
  </section>

  <section class="section" id="precios">
    <h2>Catálogo</h2>
    <div class="products" id="product-list">
      <!-- Productos se insertan desde JavaScript -->
    </div>
    <button id="checkout-btn">Finalizar compra</button>
  </section>

  <section class="section" id="entrega">
    <h2>Lugares de Entrega</h2>
    <ul>
      <li>La Paz</li>
      <li>El Alto</li>
    </ul>
  </section>

  <section class="section" id="contacto">
    <h2>Contacto</h2>
    <p>WhatsApp: <a href="https://wa.me/59163124486">+591 63124486</a><br>
    Email: veritiemagnoliakreativ@gmail.com<br>
    Instagram: @veritemagnoliakreativ</p>
  </section>

  <div id="cart">
    <h3>Carrito</h3>
    <ul id="cart-items"></ul>
    <p>Total: <span id="cart-total">0</span> Bs.</p>
  </div>

  <footer>
    &copy; 2025 Bloomi. Todos los derechos reservados.
  </footer>

  <script>
    const products = [
      { id: 1, name: "Rosa eterna", price: 150, img: "https://i.imgur.com/UDt4ZIT.jpg" },
      { id: 2, name: "Arreglo eterno", price: 90, img: "https://i.imgur.com/UpnpOeE.jpg" },
      { id: 3, name: "Caja de rosas eternas", price: 250, img: "https://i.imgur.com/o8hI2Tt.jpg" },
      { id: 4, name: "Ramo buquette", price: 150, img: "https://i.imgur.com/UDt4ZIT.jpg" },
      { id: 5, name: "Ramo buchon", price: 90, img: "https://i.imgur.com/UpnpOeE.jpg" },
      { id: 6, name: "Amigurumis", price: 250, img: "https://i.imgur.com/o8hI2Tt.jpg" }
    ];

    const productList = document.getElementById('product-list');
    const cartItems = document.getElementById('cart-items');
    const cartTotal = document.getElementById('cart-total');
    let cart = [];

    function renderProducts() {
      products.forEach(p => {
        const card = document.createElement('div');
        card.className = 'product';
        card.innerHTML = `
          <img src="${p.img}" alt="${p.name}">
          <h3>${p.name}</h3>
          <p>${p.price} Bs.</p>
          <button onclick="addToCart(${p.id})">Agregar al carrito</button>
        `;
        productList.appendChild(card);
      });
    }

    function addToCart(id) {
      const product = products.find(p => p.id === id);
      cart.push(product);
      updateCart();
    }

    function updateCart() {
      cartItems.innerHTML = '';
      let total = 0;
      cart.forEach(item => {
        total += item.price;
        const li = document.createElement('li');
        li.textContent = `${item.name} - ${item.price} Bs.`;
        cartItems.appendChild(li);
      });
      cartTotal.textContent = total;
    }

    function generateWhatsAppLink() {
      let message = "¡Hola! Me gustaría hacer un pedido de flores:\n\n";
      cart.forEach(item => {
        message += `Producto: ${item.name} - Precio: ${item.price} Bs.\n`;
      });
      message += `\nTotal: ${cartTotal.textContent} Bs.`;
      const encodedMessage = encodeURIComponent(message);
      const link = `https://wa.me/59163124486?text=${encodedMessage}`;
      window.open(link, '_blank');
    }

    document.getElementById('checkout-btn').addEventListener('click', generateWhatsAppLink);

    renderProducts();
  </script>
</body>
</html>
