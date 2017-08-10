<template>
<div class="card">
  <header class="card-header">
    <div class="card-header-title is-centered">
        {{ product.Name }}
    </div>
  </header>

  <div class="card-image">
    <img v-bind:src="product.ThumbUrl" />
  </div>

  <div class="card-content">
    <div class="content">
      {{ product.Description }}
    </div>
  </div>

  <div class="card-footer">
    <a href="#" class="snipcart-add-item card-footer-item"
      data-item-url="/"
      v-bind:data-item-name="product.Name"
      v-bind:data-item-price="product.Price"
      v-bind:data-item-id="product._id"
      v-bind:data-item-url="product.ThumbUrl"
      v-bind:data-item-description="product.Description">
      <i class="fa fa-cart-plus"></i> &nbsp;Add to cart
    </a>
  </div>
</div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      required: true
    }
  }
}
</script>
