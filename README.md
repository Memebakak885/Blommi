# Bloomi
Talvez no eres perfecta, pero eres auténtica, loca y algo rara y eso le GANA A TODO.

<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bloomi</title>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Open+Sans&display=swap">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Open Sans', sans-serif; background-color: #FAF4ED; color: #2B2B2B; }
    header { background-color: #B3507A; color: white; padding: 2rem; text-align: center; }
    nav { display: flex; justify-content: center; gap: 2rem; background: #2B2B2B; padding: 1rem; }
    nav a { color: #FAF4ED; text-decoration: none; font-weight: bold; }
    .hero { background: url('https://i.imgur.com/JZCmJxd.jpg') center/cover; height: 60vh; display: flex; justify-content: center; align-items: center; color: white; font-size: 2rem; font-family: 'Playfair Display'; }
    .section { padding: 3rem 2rem; max-width: 1200px; margin: auto; }
    h2 { font-family: 'Playfair Display'; margin-bottom: 1rem; color: #B3507A; }
    .products { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 2rem; }
    .product { background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); padding: 1rem; text-align: center; }
    .product img { width: 100%; border-radius: 10px; }
    .product button { background-color: #D4AF37; border: none; padding: 0.5rem 1rem; margin-top: 1rem; color: white; cursor: pointer; border-radius: 5px; }
    #cart { position: fixed; top: 1rem; right: 1rem; background: #B3507A; color: white; padding: 1rem; border-radius: 8px; max-width: 300px; }
    footer { background: #2B2B2B; color: #FAF4ED; text-align: center; padding: 2rem; margin-top: 2rem; }
  </style>
</head>
<body>
  <header>
    <h1>Bloomi</h1>
    <p>El regalo que no se marchita</p>
  </header>

  <nav>
    <a href="#nosotros">Nosotros</a>
    <a href="catálogo">precios</a>
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
    <p>WhatsApp:<a href="https://wa.me/59163124486">+591 63124486</a><br>
    Email: veritiemagnoliakreativ@gmail.com <br>
    Instagram: @veritemagnoliakreativ </p>
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
      cartItems.push(product);
      updateCart();
    }

    function updateCart() {
      let total = 0;
      cartItems.forEach(item => {
        total += item.price;
      });
      cartTotal.textContent = total;
    }

    function generateWhatsAppLink() {
      let message = "¡Hola! Me gustaría hacer un pedido de flores:\n\n";
      cartItems.forEach(item => {
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
