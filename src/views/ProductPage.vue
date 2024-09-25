<template>
  <div class="product-page-container mt-5">
    <div class="row">
      <!-- Imagen del Producto -->
      <div class="col-lg-6 col-md-12">
        <div class="product-image-container">
          <img
            src="@/assets/img/curved-images/curved0.jpg"
            alt="Product"
            class="img-fluid rounded product-main-image"
          />
        </div>
      </div>

      <!-- Detalles del Producto -->
      <div class="col-lg-6 col-md-12 mt-lg-0 mt-4">
        <h2 class="mb-0">Minimal Bar Stool</h2>
        <div class="d-flex align-items-center mt-2">
          <i class="fas fa-star text-warning"></i>
          <i class="fas fa-star text-warning"></i>
          <i class="fas fa-star text-warning"></i>
          <i class="fas fa-star text-warning"></i>
          <i class="fas fa-star-half-alt text-warning"></i>
          <span class="ms-2">(4.5)</span>
        </div>

        <h3 class="text-success mt-3">$1,419</h3>
        <p class="text-success">IN STOCK</p>

        <!-- Descripción del Producto -->
        <ul class="text-muted product-description">
          <li>The most beautiful curves of this swivel stool add an elegant touch to any environment.</li>
          <li>Memory swivel seat returns to original seat position.</li>
          <li>Comfortable integrated layered chair seat cushion design.</li>
          <li>Fully assembled! No assembly required.</li>
        </ul>

        <!-- Selección de Material y Color -->
        <div class="row mt-4">
          <div class="col-lg-4 col-md-12 mb-lg-0 mb-4">
            <label>Frame Material</label>
            <select class="form-select">
              <option value="wood">Wood</option>
              <option value="metal">Metal</option>
            </select>
          </div>
          <div class="col-lg-4 col-md-12">
            <label>Color</label>
            <select class="form-select">
              <option value="black">Black</option>
              <option value="white">White</option>
              <option value="brown">Brown</option>
            </select>
          </div>
          <div class="col-lg-4 col-md-12">
            <label>Quantity</label>
            <select class="form-select">
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
            </select>
          </div>
        </div>

        <!-- Botón de Añadir al Carrito -->
        <button class="btn btn-primary add-to-cart-btn mt-4">ADD TO CART</button>
      </div>
    </div>

    <!-- Productos Relacionados (Carrusel) -->
    <div class="related-products-carousel mt-5">
      <div class="carousel-container d-flex justify-content-center gap-4 overflow-auto">
        <div
          class="carousel-slide text-center"
          v-for="(product, index) in relatedProducts"
          :key="index"
        >
          <img :src="product.image" alt="Product" class="img-fluid related-product-image" />
          <p>{{ product.title }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      relatedProducts: [
        { image: '@/assets/img/curved-images/curved1.jpg', title: 'Product 1' },
        { image: '@/assets/img/curved-images/curved6.jpg', title: 'Product 2' },
        { image: '@/assets/img/curved-images/curved8.jpg', title: 'Product 3' },
        { image: '@/assets/img/curved-images/curved9.jpg', title: 'Product 4' },
      ],
    };
  },
};
</script>

<style scoped>
.product-page-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.product-main-image {
  width: 100%;
  height: auto;
  max-height: 500px; /* Aumentar la altura máxima */
  object-fit: cover;
}

.add-to-cart-btn {
  background-color: #ff4081;
  color: white;
  padding: 10px 20px;
  font-size: 14px; /* Reducir el tamaño del texto */
  width: auto;
}

.product-description li {
  margin-bottom: 8px;
}

.related-products-carousel {
  display: flex;
  justify-content: center;
  overflow-x: auto;
  padding: 10px 0;
}

.carousel-container {
  display: flex;
  gap: 20px;
}

.carousel-slide {
  min-width: 150px;
}

.related-product-image {
  height: 100px;
  width: 150px;
  object-fit: cover;
  border-radius: 10px;
}
</style>
