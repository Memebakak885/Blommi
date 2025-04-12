
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bloomi</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Open+Sans&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet"> <!-- Fuente alegre -->
  <style>
    /* Reset de margenes y padding */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    
    /* Fondo y colores generales */
    body {
      font-family: 'Quicksand', sans-serif; /* Fuente más casual y elegante */
      background-color: #FBD5E5;  /* Fondo rosa pastel suave */
      color: #333;
      line-height: 1.6;
    }
    
    header {
      background-color: #EB9AC0;  /* Títulos rosa oscuro suave */
      color: white;
      padding: 6rem 2rem;  /* Más espacio para el título */
      text-align: center;
      border-bottom: 2px solid #F3AACB; /* Rosa intermedio */
    }

    header h1 {
      font-size: 30rem; /* Aumento del tamaño 5 veces más grande */
      font-family: 'Pacifico', cursive; /* Título con fuente llamativa */
    }

    header p {
      font-size: 1.5rem;
      margin-top: 1rem;
    }

    /* Estilos del menú de navegación */
    nav {
      display: flex;
      justify-content: center;
      gap: 1rem; /* Reducir espacio entre botones */
      background-color: #F3AACB;  /* Rosa intermedio */
      padding: 1rem;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      text-transform: uppercase;
      font-size: 1rem; /* Reducir el tamaño de los botones */
    }

    nav a:hover {
      color: #F7BFD8;
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
      color: #F74780;  /* Títulos más oscuros y fucsias */
      font-size: 3rem;
      font-weight: bold; /* Negrita */
    }

    .cinta {
      border: 5px solid #F3AACB; /* Color rosa intermedio */
      padding: 10px;
      margin-top: 20px;
      font-size: 1.5rem;
      color: #F74780; /* Color rosa fuerte */
      display: inline-block;
      background-color: #F7BFD8; /* Color suave de fondo */
      font-weight: bold;
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
      max-width: 400px;  /* Imágenes más grandes */
      border-radius: 10px;
      margin-bottom: 1rem;
    }

    .product h3 {
      color: #F3AACB;  /* Resto de letras morado claro */
      margin-bottom: 0.5rem;
    }

    .product p {
      font-size: 1rem;
      color: #333;
    }

    .product button {
      background-color: #F3AACB;  /* Rosa intermedio para botones */
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
      background-color: #F7BFD8;  /* Rosa más claro al pasar el mouse */
      color: #333;
    }

    #cart {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background: #F74780;  /* Fucsia fuerte para el carrito */
      color: white;
      padding: 1.5rem;
      border-radius: 8px;
      max-width: 300px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      z-index: 1000;
    }

    #checkout-btn {
      background-color: #F74780;  /* Fresa fuerte para el botón de finalizar compra */
      color: white;
      font-weight: bold;
      border: none;
      padding: 1.2rem 2.5rem;  /* Aumento del tamaño del botón */
      border-radius: 8px;  /* Botón más redondeado */
      cursor: pointer;
      margin-top: 1rem;
      font-size: 1.2rem;  /* Aumento del tamaño del texto */
      transition: background-color 0.3s;
    }

    #checkout-btn:hover {
      background-color: #F16DB1;  /* Fucsia suave al pasar el mouse */
      color: #333;
    }

    footer {
      background: #2B2B2B;
      color: #FAF4ED;
      text-align: center;
      padding: 2rem;
      margin-top: 2rem;
    }

    /* Enlaces fucsia */
    a {
      color: #F74780;  /* Fucsia para los enlaces */
      font-weight: bold; /* Enlace en negrita */
    }

    a:hover {
      color: #F3AACB;  /* Fucsia intermedio al pasar el mouse */
    }

    /* Enlace WhatsApp */
    #contacto a {
      color: #F74780;  /* Fucsia para el enlace de WhatsApp */
      font-weight: bold; /* Enlace en negrita */
    }

    #contacto a:hover {
      color: #F3AACB;  /* Fucsia intermedio al pasar el mouse */
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
    <div class="cinta">
      Tal vez no eres perfecta, pero eres auténtica, loca y algo rara y eso le gana a todo
    </div>
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
      <li><strong>Lugares de Entrega La Paz- Zona Sur</strong></li>
      <ul>
        <li> Mega Center.</li>
        <li> Teleférico Verde (Cualquier parada).</li>
        <li> Otros.</li>
      </ul>
      <li><strong>Lugares de Entrega La Paz- Centro</strong></li>
      <ul>
        <li> Correos.</li>
        <li> Plaza del Estudiante.</li>
        <li> Stadium.</li>
      </ul>
      <li><strong>Lugares de Entrega Ciudad del Alto</strong></li>
      <ul>
        <li> Ceibo.</li>
        <li> Teleférico Morado.</li>
        <li> Teleférico Rojo.</li>
      </ul>
      <li><strong>Otros con Costo Adicional</strong></li>
      <ul>
        <li> Consultar.</li>
      </ul>
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
