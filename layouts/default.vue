<template>
  <div>
    <div class="container">
      <nav class="navbar">
        <div class="navbar-menu">
          <div class="navbar-start">
            <a href="/" class="navbar-item">Products</a>
          </div>
          <div class="navbar-end">
            <a href="#" class="navbar-item snipcart-checkout snipcart-summary">
              <span>View cart (<span class="snipcart-total-items">0</span>)</span>
            </a>
          </div>
        </div>
      </nav>
    </div>

    <section class="section">
      <div class="container">
        <nuxt />
      </div>
    </section>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.2/jquery.min.js"></script>
    <script id="snipcart" src="https://cdn.snipcart.com/scripts/2.0/snipcart.js" data-api-key="YjdiNWIyOTUtZTIyMy00MWMwLTkwNDUtMzI1M2M2NTgxYjE0"></script>
  </div>
</template>

<script>
export default {
}
</script>
