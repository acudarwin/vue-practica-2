<template lang="">
    <div class="card" style="width: 18rem" @click="() => select(product.id)">
      <div class="card-body">
        <h5 class="card-title">{{ product.nombre }}</h5>
        <img v-bind:src="product.imagen" alt="ProducImage"/>
        <p v-html="product.descripcion" class="card-text"></p>
        <div class="producto-relacionado-precio">
          Precio:{{ product.precio }} BOB
        </div>
        <div>
          <div>
            <div
              class="color-box"
              v-for="color in product.colores"
              :style="{ background: color }"
            ></div>
          </div>
        </div>
      </div>
    </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Object,
      required: true,
    },
    select: {
      type: Function,
      required: true,
    },
  },
};
</script>
<style lang="css">
.producto-relacionado-precio{
                background: orangered;
                color: white;
                text-align: center;
                padding: 10px; 
            }
.color-box {
                width: 40px;
                height: 40px;
                border-radius: 50%;
                margin: 7px;
                display: inline-block;
            }
        img {
            min-height: 150px;
            width: 100%;

        }
</style>
