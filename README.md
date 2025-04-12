<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bloomi</title>
  <style>
    /* Estilos del sitio (mantén tus estilos aquí) */
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
    <div class="products" id="product-list"></div>
    <!-- Botón para finalizar compra -->
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
    <p>WhatsApp:<a href="https://wa.me/59163124486">+591 63124486</a><br>
    Email: veritiemagnoliakreativ@gmail.com <br>
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
